Below are a series of monologues extracted from the provided transcript. Each monologue represents a relatively uninterrupted train of thought by George Hotz. The text is carefully reworded for grammar, clarity, and flow but preserves the essential ideas, realizations, insights, and attitudes. 

---

## Monologue 1 
**Context**: George Hotz opens the stream, greeting viewers and speaking spontaneously about Twitch, marijuana use on camera, streaming platforms, and revenue splits.

> **Reworded Text**  
> Good morning, everyone! It looks like this morning we have an unexpected situation: one of our usual tools (“Mar is D”) doesn’t work, but that’s all right—we’ll use whatever we can and see if we can solve the problem.  
>  
> So, who’s familiar with how to play “Press the Light Up Button”? Let’s get going. We’re pulling out all the stops, doing whatever is possible. Good morning! I see a disclaimer on the stream, probably because I might smoke marijuana while we’re live. That’s just how it goes sometimes—though I do wonder if Twitch is going to flag or ban me for it. We are in California, where it’s entirely legal, but apparently, Twitch has an issue with it.  
>  
> I’m not trying to advocate breaking terms of service, but it frustrates me: Twitch might ban me for legal marijuana use, while the platform itself takes fifty percent of the subscription revenue. I’m learning that on Twitter, streamers can get 97% of the money from subscribers. So maybe I should just move my streaming over there. Or maybe to Kick—ever heard of Kick? It’s apparently a Twitch competitor.  
>  
> I mean, if Kick gave me a deal, I’d happily switch. Let’s be real: Twitch always seemed uneasy about me smoking weed on stream. They throw up disclaimers warning people about potential drug use. And that’s only the surface issue—there’s also the matter of the split. Twitch’s 50% cut is pretty significant.  
>  
> Sure, I could get banned for saying all this, but maybe that would be fine. I’ve banned myself from casinos before to keep things simpler, so if Twitch bans me, maybe it’ll be a blessing. Honestly, they only give me half of subscription revenue, and I find that kind of unfair. Meanwhile, Kick is apparently offering people crazy splits. I don’t know if Kick is “shady,” but if they are legit, or if Twitter can offer me 97%, maybe I’ll do that.  
>  
> Twitch staff, if you happen to see this, you know what I’d like: a better revenue share than 50%. At the least, please remove that big warning that I’m doing drugs. It’s legal marijuana, and I am not actually doing anything especially scandalous.  
>  
> Negotiation attempts aside, let’s focus on the real subject today: we want to talk about reinforcement learning (RL). That’s the main thing we’re set to do, but I got sidetracked by being upset about Twitch. If Kick or Twitter calls me with a lucrative deal, I might switch. Otherwise, I’ll keep streaming here for now.  
>  
> In summary: twitch is taking a big cut, they label me as a drug user, so maybe I’ll move to another platform. Let’s also talk about RL, but keep in mind my frustration about streaming platform issues.  

**Key Concepts & Attitudes**  
- Frustration with Twitch policies regarding legal marijuana use.  
- Complaints about Twitch’s 50% subscription revenue split.  
- Openness to alternative platforms (Kick, Twitter) if they offer better deals.  
- Intention to keep streaming but readiness for a potential ban.  
- Setting up the conversation to pivot back to reinforcement learning later.  

---

## Monologue 2
**Context**: Continuing from the discussion of streaming platforms, George emphasizes negotiation, revenue splits, and his overall stance on Twitch.

> **Reworded Text**  
> Twitch, if you’re watching, I’d really love it if we could settle something fair. I mean, I’m not a small streamer. I might not be the biggest, but I draw around a thousand concurrent viewers, which has to be somewhat valuable to the platform. That number may not get me in the top ten, but it’s still nothing to sneeze at.  
>  
> If you want me to keep streaming here, you could offer me a better split than 50%. Big names apparently get 70/30, and I’d like something more along those lines. Right now, I feel stuck in some backroom scenario where I can’t get partner status because they don’t like me or they have unknown rules for picking who gets 70/30. Meanwhile, if there’s a platform like Kick that’s willing to hand me a strong deal, well, that might solve things.  
>  
> Of course, I don’t know much about Kick. They could be shady. Maybe they’re tied to some crypto gambling site. But if they approached me legitimately, I’d consider it. Right now, I’m also curious about Twitter (or X), because apparently they give a large portion of subscription funds back to creators—some say up to 97%. However, I’m not sure about their streaming features, whether they have chat or how subscription gating would work.  
>  
> The bottom line is that I’m irritated about that marijuana disclaimer, especially since it’s legal where I live. Twitch feels inconsistent about their rules, and I don’t appreciate having “Intoxicated Streamer” disclaimers slapped on me as if I’m doing something extreme. I’m not out here “banging seven-gram rocks” like Charlie Sheen once said. I’m just having a bit of weed while working on code.  
>  
> So that’s the gist: I want a better deal, and if they don’t like that, they might ban me. That’s okay; I’ll live. But for the record, I believe that in the science and technology section, I’m one of the top streamers in terms of viewer count, so I do feel justified in asking for better terms.  

**Key Concepts & Attitudes**  
- Desire for a better revenue split, possibly 70/30.  
- Skepticism about Kick’s reputation but openness to hearing offers.  
- Curiosity about Twitter’s streaming possibilities.  
- Annoyance regarding Twitch’s inconsistencies in policies.  
- Self-confidence in his position and viewer numbers on the platform.  

---

## Monologue 3  
**Context**: George transitions into explaining what the day’s stream is actually about: reinforcement learning, stable baselines, and a simple game called “Press the Light Up Button.”

> **Reworded Text**  
> Let’s get back to our main topic: reinforcement learning. We spent time building a little game called “Press the Light Up Button.” In it, one of several buttons lights up, and you must press the corresponding button to get a reward. We coded the environment ourselves, and the challenge now is to see if we can train an RL model to solve it.  
>  
> I decided to try Stable Baselines 3, which is a popular Python library for RL. It’s convenient because it has well-tested implementations of algorithms like PPO, A2C, and SAC. Using stable baselines, we found that it learned the “Press the Light Up Button” game almost immediately for small scenarios (like if there are only two or three possible buttons). With something bigger—say 10 or more—it still learns, but it takes more time.  
>  
> Then there’s “hard mode.” In “hard mode,” the correct button changes from one step to the next in a non-trivial way. Using the basic algorithms, we noticed the model doesn’t quite learn it. It might be that “Press the Light Up Button (hard mode)” requires some form of memory or recurrent policy. Or perhaps we need more training time.  
>  
> This is typical with RL: it can handle a simpler version just fine, but if you add temporal complexity—like a rule changing step by step—it often doesn’t pick it up with a basic approach. That might require a more advanced architecture or more training steps.  

**Key Concepts & Attitudes**  
- Explanation of a custom RL environment: “Press the Light Up Button.”  
- Observing stable baselines learning the simple version quickly.  
- Harder modes require memory or advanced methods.  
- Acknowledgment that RL struggles with tasks that have changing rules.  

---

## Monologue 4  
**Context**: George reflects on the challenges of debugging RL code, especially in a personal library like Tinygrad. He discusses the importance of building stable infrastructure.

> **Reworded Text**  
> One big realization I’ve had is that reinforcement learning is challenging to debug. There are so many points of failure: there could be a bug in the environment, a bug in the RL algorithm, or a bug in the neural network library itself. Yesterday, I was flailing around trying to implement a Decision Transformer in Tinygrad, and it never worked. I couldn’t be sure if my environment was wrong, if my RL logic was flawed, or if Tinygrad itself had an issue.  
>  
> This is analogous to the problem you see in some developing regions—like a place where roads have huge potholes named “The Ancestor” because it’s been there so long. You realize it’s not that the people there are incapable; it’s that everything is patchy and infrastructurally unsound, so they put in extra effort to do basic things. With RL, if you don’t have robust, tested infrastructure, you end up spending all your time hacking around uncertain problems.  
>  
> That’s why libraries like Stable Baselines are valuable: someone has presumably tested them, so it gives you confidence you’re not sinking your time into a black hole. The code might be large, but at least you know it can run reliably, and the results line up with known benchmarks. That’s what I was missing when I attempted Decision Transformers in my own code. I had no guarantee of correctness anywhere in the pipeline.  

**Key Concepts & Attitudes**  
- The difficulty of debugging RL due to multiple layers (environment, algorithm, library).  
- The need for strong infrastructure to avoid endless “patching.”  
- Appreciation for stable, well-tested RL libraries like Stable Baselines.  
- Reluctance to rely on personal code for complex tasks without thorough validation.  

---

## Monologue 5  
**Context**: George describes in detail how he tried to implement PPO, policy gradient methods, and advantage actor-critic in Tinygrad, running into repeated issues.

> **Reworded Text**  
> I’ve been wrestling with a PPO implementation. At first, I had some bizarre bug where the “old policy” log probabilities weren’t being computed properly, so the ratio in the PPO loss was broken. Somehow, it still learned simple tasks, even though I later discovered it was basically ignoring half the equation. Then I discovered that I hadn’t detached certain value function calls, meaning the advantage calculations were feeding erroneous gradients everywhere.  
>  
> What amazed me is how these obvious bugs can go unnoticed because RL is so noisy and occasionally learns anyway. You can thoroughly break your objective function, but it still stumbles into a solution for a simple environment like CartPole. You fix the bug and expect results to improve drastically, yet things sometimes stay the same or even get worse. That can be maddening.  
>  
> It gets even more complicated if you try to do something like softmax temperature or clipping. One tiny discrepancy in your log or ratio calculations can throw the entire training off. And often, you can’t see it clearly unless you deeply inspect the gradients or track bizarre metrics to figure out where your agent is stuck.  
>  
> My plan now is to double down on careful testing. If I want to fix the RL code in Tinygrad, I need to test each function systematically—like checking whether “log softmax” does exactly what we expect, or verifying that “detach” genuinely stops gradients. We found so many fundamental mistakes that it’s no wonder everything’s shaky.  

**Key Concepts & Attitudes**  
- Struggles with a PPO implementation and the difficulty of debugging RL code.  
- Surprising resilience of simple RL tasks despite major bugs.  
- Complexity of small details: log-prob calculations, ratio clipping, detach mechanics.  
- The importance of systematic testing and verifying each piece of the pipeline.  

---

## Monologue 6  
**Context**: George compares and contrasts Tinygrad with PyTorch, demonstrating that porting code to PyTorch often reveals the same problems but at a much faster compute speed.

> **Reworded Text**  
> Another step I tried was rewriting my minimal RL example in PyTorch to see if it suddenly worked perfectly. It turned out it had the same issues. PyTorch is definitely faster, no question—on small networks, it’s blazing, while Tinygrad is relatively slower. But it didn’t magically fix the RL logic. I still saw numerical instabilities. I still saw poor results on slightly more complicated tasks.  
>  
> That actually gave me a bit of relief: at least Tinygrad isn’t alone in failing to learn. If you replicate your mistakes in PyTorch and get the same outcome, it means your conceptual or coding approach is likely to blame, not your library.  
>  
> It also highlighted how finicky RL can be. If your learning rate is slightly off or your network architecture has one too many layers, it can spiral into nonsense. And with all the random noise in sampling episodes, if you see success on one run, it might just be a lucky seed. That is the frustrating reality of RL.  

**Key Concepts & Attitudes**  
- Using PyTorch to cross-check if the code or logic is at fault.  
- Finding the same RL difficulties in PyTorch—so it’s not a Tinygrad-exclusive problem.  
- Acknowledging PyTorch’s speed advantage.  
- Recognizing RL’s heavy dependence on hyperparameters and random seeds.  

---

## Monologue 7  
**Context**: George attempts to systematically fix or simplify the RL approach, reverting to very basic policy gradient setups, yet still sees unpredictability as soon as the environment or network gets more complex.

> **Reworded Text**  
> I went back to a basic approach—vanilla policy gradient with no advantage function, just the plain old “multiply reward by log probability” and do gradient ascent. I used a simple environment like “Press the Light Up Button” with only two choices, and it learned quickly. Great—makes sense. If I bumped it up to three or four choices, it became unreliable or took forever. That’s puzzling because it’s only a modest jump in complexity.  
>  
> I realized part of it is how random the environment is. If the agent doesn’t sample the correct button enough times early on, it doesn’t get a strong learning signal. Another part is how subtle everything can be when your model is small or your initialization is unlucky. I also tried linear layers without activation to see if it could basically learn an identity matrix—and for two buttons, it did. For four or more, it often got stuck.  
>  
> All this suggests that RL can be extremely sensitive. Even in what looks like a trivial environment, if you have four actions, the gradient updates might not align enough times to produce a consistent solution. Then you add critics, advantage functions, or PPO clipping, and it becomes even more brittle.  

**Key Concepts & Attitudes**  
- Testing the simplest “vanilla policy gradient” approach.  
- Seeing how small increases in environment complexity cause training instability.  
- Observing the significance of random sampling in early training.  
- Realizing how easily an RL approach can get “stuck,” even in seemingly simple tasks.  

---

## Monologue 8  
**Context**: George transitions into a lengthier reflection on the underlying nature of reinforcement learning, referencing how it remains unreliable and difficult, especially on tasks like Lunar Lander.

> **Reworded Text**  
> Lunar Lander is that classic benchmark that feels like it should be easy enough. I see it partly land, hover, or sometimes crash in ways that suggest it learned something, but it’s never a clean, consistent solution. You watch the reward graph fluctuate up and down. Occasionally it nails a perfect landing—then it reverts to flailing around.  
>  
> People talk about how we’re on the verge of AGI, but if you try to do reinforcement learning in a naive way, you’ll find it’s nowhere near robust. You realize how fragile these methods still are. Gans have that same instability problem, and RL is similar. It’s basically two (or more) networks in some dynamic interplay—an actor and a critic—and the slightest mismatch in updating can cause the policy to collapse.  
>  
> Then we’re left with hyperparameter hunts: adjusting the discount factor, replay buffer size, learning rate, network size, entropy coefficients—on and on. Yes, we sometimes see miraculous results after large-scale searches, or we read big success stories in specialized tasks. But in typical small projects, you often end up with a system that partially learns or repeatedly forgets.  
>  
> It’s honestly humbling. Every time I think “this is it, we’re about to see general RL solve everything,” I’m reminded that on something like Lunar Lander, it might do decently but not reliably.  

**Key Concepts & Attitudes**  
- Challenges in training RL on Lunar Lander and seeing erratic performance.  
- Skepticism about claims of near-term “AGI” in light of RL’s brittleness.  
- Comparison of RL instability to the instability seen in GANs.  
- The reality of extensive hyperparameter tuning to reach success stories.  
- A humble perspective on RL’s real-world reliability.  

---

## Monologue 9  
**Context**: George concludes the session with a final commentary on how these difficulties illustrate the fundamental state of RL. He jokingly references not being able to go for lunch until the agent lands the craft perfectly.

> **Reworded Text**  
> I finally just let the agent keep training, hoping for the perfect Lunar Lander touchdown before I ended the stream. Of course, that may or may not happen. Sometimes the agent starts hovering forever, sometimes it picks up big negative rewards. Occasionally, it nails a decent landing. That’s RL in a nutshell: you might wait and watch for hours in the hopes of that shining moment of competence.  
>  
> People ask, “Why not just do direct trajectory optimization or carefully script something?” Because that’s not the RL spirit. RL is about emergent behavior learned from experience. You can’t cheat by giving it the solution. Yet, ironically, if we had just coded the control logic by hand, it would land with no fuss.  
>  
> In the end, the frustration is real: RL is time-consuming, hyperparameter-sensitive, and not guaranteed to converge. Sometimes it feels like we’re just sampling random seeds until one hits. That’s why I keep repeating that RL is “dumb” or “not reliable.” Yes, for some tasks it’s revolutionary, but for a great many others, it’s just painfully unstable.  
>  
> With that, I’m off to get a sandwich. I’ll consider it a victory that we got even one decent landing. Maybe that’s all RL is good for at the moment: celebrating those small wins when they finally emerge.  

**Key Concepts & Attitudes**  
- Waiting for a perfect episode feels emblematic of RL’s unpredictability.  
- Emphasizing the “emergent behavior” philosophy behind RL vs. direct coding.  
- Reflecting on RL’s time cost and instability.  
- Ending with the notion that occasionally seeing success is the best you can hope for.  

---

### Final Note on the Monologues
These nine monologues capture George Hotz’s main trains of thought: from his commentary on Twitch’s revenue model and policies, to the intricacies and frustrations of reinforcement learning, the challenge of debugging, and the ultimate lesson that RL is still fundamentally unreliable for many tasks—especially without massive hyperparameter searches and well-tested infrastructure.