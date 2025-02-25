Below, you will find selected “monologues” from the transcript—long, relatively uninterrupted segments in which George Hotz shares coherent thoughts or opinions, teaches something, or makes realizations. They have been edited for grammar and clarity to make them more readable, but the key concepts, insights, and attitudes remain true to the original. Each monologue is labeled, followed by a brief summary of its main topic(s). The text then presents the monologue in a more polished, “letter-like” style.

---

## MONOLOGUE 1
**Topic Summary:**
George Hotz’s perspective on AI “doping” in coding competitions and Advent of Code, his belief that efforts to restrict AI usage are misguided, and his view that it mirrors the debate over doping in sports.

**Monologue (Edited for Clarity):**

> **“Here’s my take on AI and Advent of Code: it’s basically doping. In professional cycling, I’ve always felt they should allow doping outright because it’s silly to ban it—if you want to stay competitive, you have to do it. The situation with Advent of Code is the same. If you try to do those puzzles without using AI, you’re just not going to compete with those who do.**
>
> **I used to do Advent of Code manually, and I performed pretty well for a couple of years. But this year, when I tried the first few puzzles without AI, I realized I was no longer truly competitive. That’s what changes once AI is introduced: the contest becomes more about who builds the best automation with these large language models or coding assistants. Restricting it feels as pointless as trying to restrict doping.**
>
> **People ask me which AI model I use. I’m not too specific about it, but obviously I’ve tried many. You have to move fast if you want to get a good rank on the leaderboard—piping your solutions to an API, for instance—and I find that open-source or commercial AI are all fair game. As soon as you say you want ‘pure’ human effort, you’re just banning what’s obviously the new baseline. We might as well all embrace the technology. That’s why I compare it to cycling: doping used to be frowned upon, but in my opinion, it would be easier if they just allowed it, or at least recognized that it happens.**
>
> **So, yes, AI is doping for coding competitions, and I’m personally fine with that. The key is how quickly you can adapt your entire workflow to incorporate it. That’s the new skill. The playing field changes, and we all deal with it.”**

---

## MONOLOGUE 2
**Topic Summary:**
George Hotz briefly reflects on living in Hong Kong, his upcoming travel plans, and how he feels about returning to San Diego.

**Monologue (Edited for Clarity):**

> **“I’m in Hong Kong now—I live here for the moment. Honestly, I think Hong Kong is part of the future: it’s an interesting hub, and it gives me perspective on what’s going on outside the United States. I still travel back to the U.S. occasionally, though. In fact, I’m flying back to San Diego tomorrow. We have a holiday party at comma, and I want to meet with some people from tiny corp. I’m excited for it—I have big plans for the next year, and I’d like to check in with the team.**
>
> **It can be tough balancing time between Hong Kong and the U.S., but I’m used to traveling around at this point. It’s great that the world is so connected now, or at least I feel that way. Also, people ask about language barriers: I speak a bit of Mandarin, maybe at the same skill level that I play Factorio, which is to say not super well. Still, it’s enough for day-to-day life. Hong Kong is also extremely English-friendly, so it hasn’t been a problem. But yeah, that’s the plan: head back for the party, then come back here.”**

---

## MONOLOGUE 3
**Topic Summary:**
George Hotz discusses the new ChatGPT (and other large language models), how older versions changed, and why he is willing to pay for AI access. He also touches on how these tools affect coding.

**Monologue (Edited for Clarity):**

> **“I recently bought the new ChatGPT upgrade. My impression is they made the old ‘GPT-4 with 32k context’ or older models a bit less useful, so you kind of have to pay to get the best version. I don’t mind paying 20 dollars a month or more if it means I have consistent, unlimited access to the best model. I do the same with Claude, too—I’ve got a subscription there because I want to compare performance.**
>
> **For me, the big deal is that these tools can write code well. GPT-4 is probably the first model that really can code effectively. Before that, AI felt like a novelty for coding—it might have helped with certain boilerplate, but GPT-4 changed the game. Now, if I’m doing something like Advent of Code or building a quick prototype, the AI is unbelievably helpful. It really is an augmentation of your programming ability.**
>
> **Yes, we can talk about whether this is ‘cheating’ or not, but I see it as the new norm. You embrace it or you get left behind. It’s no different from using advanced libraries back in the day: eventually, it just becomes standard practice to rely on better tools. If people say the older GPT was better, I can see that argument, but I prefer the new one because at least it’s consistent, and I’m happy to pay for something that saves me time.**”

---

## MONOLOGUE 4
**Topic Summary:**
George Hotz explains recent work on his “tinygrad” project, discussing how shape tracking, loop operations, and unified operation primitives (UOPs) form the core. He briefly shows how the code compiles and how the new approach removes a bulky file.

**Monologue (Edited for Clarity):**

> **“One of the biggest projects we’re tackling in tinygrad is deleting this massive file that used to hold a bunch of complicated logic. We realized we just don’t need most of it once we shift to a more unified approach. The main abstraction now is the UOP, which is basically how we represent every operation within tinygrad. We have shape trackers to handle indexing and expansions, and then we do these passes that lower everything into fundamental loops.**
>
> **For example, we start with a high-level operation, like a ‘map and multiply’ or a ‘reduce.’ Then we do a pass that expands it into these shape trackers, which keep track of how the data is laid out and how to do the indexing. Next, we unroll any vectorization, do constant folding if we can, remove any no-op expansions, and finally spit out a single block of code that runs everything on the GPU. It’s kind of cool to watch if you turn on ‘viz’ mode. You see each transformation step from something abstract to something very explicit.**
>
> **We used to have a file with thousands of lines of one-off tricks and special cases, but now we have these systematic passes that just handle the complexity automatically. It’s a much cleaner way to build a compiler for neural network ops. Eventually, I want it to be so straightforward that you can basically read the entire output kernel and see exactly how your layer is computed. The big idea is that if you do everything systematically, you can remove a lot of patchwork code. That’s why we call it the ‘deletion of a big file’—we just don’t need it anymore.”**

---

## MONOLOGUE 5
**Topic Summary:**
George Hotz’s philosophy on internships and contributing to open-source projects, alongside a brief comment about open collaboration and AI making coding more accessible.

**Monologue (Edited for Clarity):**

> **“Sometimes people ask me, ‘How can I get an internship with you or your company?’ And I always say: ‘Contribute on GitHub first.’ That’s my general rule. Show me that you can add value by pushing code, fixing bugs, or implementing features. If you can do that, you’re effectively already interning—just without the formalities. Then it’s a no-brainer to bring you on.**
>
> **I get a lot of messages that say, ‘Hey, can I just join and learn from you?’ But we live in a world where AI is readily available for coding. If you have the drive and you can use AI tools for scaffolding, you can learn almost anything you need. There’s not much of an excuse to say you don’t know how to get started. You can jump in, read the issues on a GitHub project, ask relevant questions, let the AI help you get a baseline fix, and keep improving. Once you demonstrate that you’re helpful, sure, I’ll talk about an internship.**
>
> **I guess the core idea is: you prove yourself by doing. If you love a project or a company’s vision, just start contributing. That’s how many people on our team joined—they added value, we noticed, and it made complete sense to make it official.”**

---

### Notes on the Process
1. **Selection Criteria:** These monologues were chosen because each section shows George Hotz sharing a coherent line of thought: teaching something, reflecting on a subject (e.g., doping in competitions, living in Hong Kong, tinygrad’s design), or providing opinions on AI and internships.
2. **Edits Made:** The transcripts were heavily cleaned up for grammar, sentence structure, and coherence. Repetitive filler words or stammering have been removed, and partial or repeated phrases (“for for for”) have been omitted.
3. **Key Concepts Preserved:** Despite changes for clarity, the underlying points remain:  
   - AI usage in coding competitions as “doping”  
   - George Hotz’s perspective on Hong Kong and travel  
   - Willingness to pay for newer, better AI models  
   - Technical insights into tinygrad’s compiler passes  
   - Philosophy on open-source contributions and internship offers  

These five monologues capture much of George Hotz’s main commentary, opinions, realizations, and teaching moments from the provided transcript.