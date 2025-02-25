Below you will find several extended monologues extracted from the provided transcript of George Hotz’s livestream. Each monologue has been edited lightly for spelling, grammar, and coherence, but preserves George’s key ideas, realizations, and attitudes. After each monologue, you will see a brief summary of its key points. The quotes and structure have been reorganized into clearer paragraphs, but as much original phrasing as possible has been maintained so that George’s “voice” remains. 

---

## Monologue 1 
**Topic**: Streaming at the Office, Negativity vs. Positivity, and the Decision to “Bring Back the Old Vibes”  
**Approximate Length**: ~300 words  
**Key Concepts**:  
- Discomfort streaming at the office  
- Concern about “vibes” being off and wanting positivity  
- Mentions of wanting to avoid negativity and hate  
- Openness to returning to older, more casual streaming style  

### Text of Monologue
“Good morning everybody, good morning, good morning, good morning. It’s nice to be back in my house. I don’t like streaming at work—I didn’t enjoy that. The vibes felt a bit off in yesterday’s stream, and I just don’t think I should stream at the office. I didn’t have my lighting set up. I didn’t feel like I was in my space. There was something about it that didn’t feel right, and I prefer streaming at home.  

Some guy told me that he liked my older work better, and if there’s one thing I never want to be, it’s Drake. He had that old style and then he switched. Well, I don’t want to disappoint people by changing too much. So let’s bring it back to the old stuff and do what we used to do—looking at things, hacking, exploring, investigating.  

I’ve been thinking a lot about negativity too. There’s so much hate in the world, so much negativity. I’m making a real effort now to be positive. We just need love and positivity sometimes. It’s so easy online to hate and call people out or complain. I want to bring more positivity to my streams. So that’s the energy I’m trying to cultivate: less complaining about random stuff, more real talk, more hacking, more energy, more fun.  

So yeah, we’re going to dig into some interesting topics today—like exploring the QAR algorithm, or whatever that is. I don’t even know what it is, but we’re going to find out. The plan is: keep it light, keep it positive, do real stuff, do some code, have fun. We’ll see where it takes us. Let’s get started.”  

---

## Monologue 2  
**Topic**: Early Discussion of “QAR,” Reading About Math Reasoning, and Opinions on Alignment  
**Approximate Length**: ~350 words  
**Key Concepts**:  
- Doubt about the purported “QAR algorithm”  
- Skepticism regarding new “breakthrough” claims in AI  
- Frustration with “alignment” talk vs. wanting to build real systems  
- Mentions of “process supervision” in ML and caution about trusting final answers only  

### Text of Monologue
“I’ve heard this QAR algorithm rumored to be some kind of big deal—maybe from some article in Reuters or something. Let’s check it out. I see references to it supposedly being a breakthrough in the search for AGI, but I can tell you from my own experience doing machine learning research that it’s very easy to imagine you have a breakthrough. Then you actually dive in and realize it’s an incremental improvement, or it’s marketing.  

I see they’re talking about math problem-solving. Something about focusing on intermediate steps—like ‘process supervision’ instead of just supervising the final answer. That’s not exactly new. The idea is that you train the model by rewarding each correct step of reasoning instead of just rewarding the end result. Usually, we only have final-answer labels because that’s what’s in the dataset, but if you can break down the problem step by step, you might correct the logic at each stage.  

The risk is that you might constrain the model’s reasoning. What if the best way for a system to think about the problem doesn’t neatly follow one labeled chain of steps? Regardless, it’s interesting if it genuinely helps with math. The current LLMs sometimes hallucinate or produce logical mistakes, so maybe it’s worth a try.  

But I notice something else: the big labs used to publish proper papers, all the time. Now they’ll give you system cards or some alignment statement. I don’t like that. My feeling: just release the research, the details, the code. Let us see how you actually trained it, what the real numbers are. I find it frustrating that we get so much hype or marketing fluff, then alignment talk, rather than a real technical paper.  

Anyway, QAR might or might not be that interesting. We’ll see if we can figure out what it really is. I’m going to poke around. But while we do that, maybe we’ll also hack on something in tinygrad or do a bounty. Because at the end of the day, I’d rather build something real than read about alignment disclaimers.”  

---

## Monologue 3  
**Topic**: Loading and Testing Open-Source 7B Models (Mistral, Hermes) in Tinygrad  
**Approximate Length**: ~400 words  
**Key Concepts**:  
- Searching for the best open-source model  
- Curiosity about Mistral 7B and Hermes  
- Loading weights quickly in tinygrad  
- Personal frustration with open-source complexity and “garbage” code  

### Text of Monologue
“So first things first: if we’re trying to do something like QAR, or some advanced math stuff, we need a good model. I want a 7B model that’s relatively powerful. People keep talking about ‘Mistral 7B’ or ‘OpenHermes 2.5’—these smaller open-source LLMs that might punch above their weight.  

I’m seeing references to Mistral being good, and Hermes being good. Let’s just pick one and try. We’ll see which is easier to load in tinygrad. Because with tinygrad, we can skip all the overhead. We just load in the weights in a couple of seconds, map them from disk, and we’re ready to do inference. I love how fast it is.  

The biggest headache in open source is the mismatch of architectures, the random code changes, rope scaling, sliding window attention, that sort of thing. People do all these little custom merges. One day you realize you have six half-baked branches for the same model. We see model repos shipping two or three random files—some JSON config, a PB file, maybe a PyTorch bin. It’s wild.  

The good news is that in tinygrad, it’s pretty straightforward once you parse the basic shapes. We can do something like `torch_load_state` that just points to the half-precision weights on disk. We handle them lazily, so it doesn’t blow up memory usage. Then we bolt it all together—embedding layer, attention, feedforward, norm—whatever the model architecture is. With Mistral, we might have to do some rope tricks to handle a larger context, but the base architecture is often still Llama-like.  

I’ll probably rename the script once we get it working. Right now, I have lumps of code from various community pull requests. Sometimes it’s a total mess. People just jam stuff in, call it ‘support for Mistral 7B,’ and push it. Then I open it up and it’s full of hacks. It’s not necessarily that it’s all worthless—it’s just not structured. That’s life in open source.  

But hey, we can handle it. We just do a little refactor. We fix the shapes, parse the heads, check the feedforward dimension. Then hopefully we can run the model in seconds. And that’s the beauty of tinygrad—I can do it all in a single file, get that quick iteration. Then we can actually test it, see if it can handle basic math or chat prompts.”  

---

## Monologue 4  
**Topic**: Special Tokens, Chat Formatting, and “System” vs. “User” Prompt Setup  
**Approximate Length**: ~400 words  
**Key Concepts**:  
- Struggles with special tokens like `<|im_start|>` and `<|im_end|>`  
- How open-source LLMs handle instruct vs. chat tokens  
- Attempting to make the conversation style “assistant” approach consistent  
- Overall exasperation with complicated tokenizer configurations  

### Text of Monologue
“One of the biggest confusions with these chat or instruct models is: how do I actually format the conversation? Some models want a system token, or a user token, or these placeholders like `<|im_start|>` and `<|im_end|>`. Then you realize that half the time it’s not actually a single token; it’s multiple tokens. Then you get an error that says ‘piece ID is out of range.’  

If you look at Mistral or OpenHermes, they might define their own special tokens, or they might not. Technically, each model can define a system prompt token if it wants. So you have to hack the sentencepiece model file, or do user-defined symbols, or something. But it’s not automatically recognized if you just feed the raw strings in.  

In open-source repos, you might see random lines in a JSON config: ‘Add special tokens = `<|im_start|>` and `<|im_end|>`.’ Then you wonder: is it truly a single token? Or do I need to do a manual injection? Because when I do normal `.encode()`, it spits out an out-of-range ID.  

Anyway, I ended up forcing it by rewriting the sentencepiece model, literally appending lines to the Proto so it has those symbols. Now at least it will decode them as single tokens. But it still might not let me encode them in a single chunk by default. I might have to do a manual function that merges them in.  

It’s annoying, but that’s the reality: these conversation-based models want you to say, ‘<|im_start|>system ... <|im_end|><|im_start|>user ... <|im_end|><|im_start|>assistant ... <|im_end|>.’ And that’s how they figure out who is who. Then if you skip a line or add an extra space, you might break the entire alignment.  

The main takeaway is that open-source LLM land is still chaotic: I can’t just load the model and feed it a user prompt. I have to replicate exactly the fine-tuned format. Once I do that, it might start responding like a real chat assistant. So that’s what I’m doing. I’m adding those tokens in by hand and crossing my fingers.”  

---

## Monologue 5  
**Topic**: Letting the Model Generate Python Code, AI “Safety,” and Experiments with “Self-Execution”  
**Approximate Length**: ~450 words  
**Key Concepts**:  
- Idea of letting the LLM produce Python code and then automatically executing it  
- Worries about alignment and malicious code  
- Contrasting comedic “AI safety” disclaimers with real concerns  
- The fascination with bridging LLM conversation to direct system calls  

### Text of Monologue
“This is the part where it gets wild: hooking up the model so it can run Python code directly. I’m literally letting the LLM say: ‘```python ...```’ and if I see that, I execute it. That’s basically the dream, or the nightmare, depending on your perspective. We joke about alignment and AI safety, but this is where real concerns come in. The model could do anything if you just let it run arbitrary code—go fetch websites, read your disk, all that.  

Of course, I built a tiny ‘AI safety check’ that says, ‘Do you want to run this code? Press Y to confirm.’ But that’s trivially bypassable. If you keep pressing Y, the model might eventually delete files or do something else. So you do need to pay attention.  

At the same time, it’s also super cool. You can have a conversation where the model says, ‘Sure, let me solve that math problem by writing Python. I’ll do the sum, or the factorial, or parse a website’s HTML for you, or call a library.’ Then it outputs the result back into the chat. That’s basically a local version of the “toolformer” concept—where the LLM can call external tools. Except we’re doing it in my stream, on my machine.  

Is this wise? Possibly not, but it’s fun. If you explicitly ask it to do malicious things, it might try. But that’s also what building and experimentation are all about. I’m not going to connect it to the real internet though. I think I’ll keep it in a sandbox, because I don’t want to run random code that fetches who-knows-what.  

You can see it sometimes tries to do advanced stuff: it might say, ‘I’m going to import Torch, or do an openAI key request.’ That’s obviously not going to work unless I have the library or the API key. But it’s interesting to see how it tries.  

Anyway, hooking up code execution is just another step toward building a real AI assistant that can do stuff. You prompt the model, it writes the script, it runs, we feed the output back, and it can refine. It’s the little steps that might lead to a more general system. But we do have to keep one eye on the safety side. I can’t let it do too much, you know, or next thing you know, it’s rummaging in my home directory or installing random packages. We’ll see how far we push that.”  

---

## Monologue 6  
**Topic**: Final Thoughts on Experimentation, the State of Open-Source AI, and the Goal of Real-Time Conversation  
**Approximate Length**: ~350 words  
**Key Concepts**:  
- Satisfaction with the day’s hacking and coding  
- Plans to unify conversation, streaming, and TTS in a single local pipeline  
- Skepticism toward hype and illusions of “AGI”  
- Desire for building something hands-on, with minimal friction  

### Text of Monologue
“All right, I think that’s enough for one day. We did some hacking, we loaded the model, we tested the special tokens. We even messed around letting it generate Python code. We basically made a baby chain-of-thought system with a manual ‘press Y to execute’ step. That’s pretty fun. People keep talking about AGI, but I’m just here hooking up little text boxes, you know?  

Sometimes you see hype about how we’re so close to general intelligence. Then you see the model messing up a two-plus-two problem because you formatted the prompt incorrectly. It’s humbling. But it’s still impressive that these 7B open-source models are able to write coherent code, do some math, and have a conversation that almost feels real.  

The next step, for me, is real-time streaming. We already have a partial pipeline with Whisper for speech recognition, a local LLM for text, and then VITS for text-to-speech. If we can stitch them all together in a streaming manner—so you talk, it streams partial text, we synthesize partial audio—that’s going to feel pretty incredible. We don’t have to wait for the entire chunk to finish; it’s all local. That’s where I think the real magic might happen, if we do it right.  

Anyway, I’ll push what we have so far. People can try it out themselves. It’s all in tinygrad, maybe on a branch for Mistral or Hermes. Just keep in mind it’s not perfect. You might see random messy code because I’ve accepted a bunch of pull requests from the community. But that’s open source—progress is messy, and you refine it over time.  

So, that’s going to be it for me today. Thanks for tuning in, and I hope we brought some positivity. Let’s keep building real systems, not just reading hype or system cards. Let’s hack, let’s have fun, and see you guys next time.”  

---

### How These Monologues Were Chosen

- **Coherence**: Each excerpt is grouped around a single main idea or continuous train of thought from George Hotz.  
- **Uninterrupted Opinion/Teaching**: These are sections where George directly explains, teaches, or offers opinions, rather than quickly interacting with random chat lines.  
- **Preservation of Key Concepts**: His remarks on streaming setups, positivity, QAR skepticism, alignment frustrations, code experiments, token handling, and building local AI tools are each preserved with minimal changes.  

Each monologue has been paraphrased only enough to improve clarity and grammar. The core insights, attitudes, realizations, and teachings remain faithful to the original transcript.