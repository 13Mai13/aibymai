---
title: "Why AI doesn't make you better"
date: 2026-03-24
tags:
    - LLM
    - AI
    - Ways of working
---

Couple caveats before stating: (1) When we talk about AI we refer to Large Language Models of general use (ChatGPT, Claude, Gemini,..) (2) I work in tech, and even if I believe this is true in other fields too, I can only speak about what I've seen in that field. 

## What AI provides

Is constantly evolving in features, but on its essence it can: read and write for you. When it reads for you, it can search, gather context from multiple different tools used to tarck work (Jira, technical documentation, how-to guides, codebases) or parse extensive documentation (legal contract). When it writes, it can write almost anything you've asked for with the context that you've given, it can even sound the way you do if enough examples are given. 

So far, none of the task sound specially catastrofic, right? They are not. But when you ask AI to do any of those, it comes with some added interets. 

It amplifies you. That's the best word I can find, with your goods and your bads. Just like when playing the guitar you don't lean the hability to play more songs with an amplifier, the techique must be there first, the amplifier would make you be in more places, or sound louder, but your mistakes will be louder too. 

It hallucinates [Insert reference]. In plain english mean it would give untrue facts about the task you've asked it to write about. Some of them may be very obvious, but not all. Even if is true that they keep improving, is actually quite easy to spot when an LLM wrote something if you truly know the person and the context. Incoherences appear. 

It sounds like you. A very common way to stop hallucinations [Insert reference] is to give AI better examples in the prompt [explain what a prompt is], this way AI can imitates those examples and generates a new text that is closer to them. This examples are kept on the context window [explain what that is] so AI tries to keep that "style" in memory in order not to make the same mistakes again. This isn't something negative, unless you combine it with the previous pharagrah of, AI will introduce untruth facts. 

It's desinged your you to like it [Find better research here]

Even at this point one could say, well the interets aren't that high - And I'd get it. We've all have come across some flavor of "automate the boring stuff". But let's evaluate a bit deeper what are we trying to automate: read and write. 

## Is this just about read and write? [I need another title]

As you may have guessed. No. That's an over-simplification. 
I think is important to understand what does AI do, and where is great. AI evaluation is one of the hardest problem to solve in general knowlege AI [Cite Chip Huyen's book], the main reason behind it being - Is really hard to evaluate an _open ended_ task. Imagine you want to write a reply a email saying you can't have a meeting in the proposed time and you need to have it in another one, well there are multiple combinations of words you can use, phrases you can make in order to achive that goal. There is no obvious "one mail is better than the other" ranking when both are good - even for humans. 

But the two examples above, are still quite scoped. Where is where the amplification can go wrong. Coding, can or can't be an _open ended_ task depending on how easy it is to verify. David Beazly has a great video about it - Intro of pycon sri lanka named the problem with the problem [https://www.youtube.com/watch?v=t-IUY6QrJyU]. 

Let's dive a bit into this with a generic task. You've agreed with your project managet that need to create a new data pipleine to populate a dashboard. Now we are going to have two alternative ways of working: A & B. 

A will draft some requiremets: How will the users consume the data, which is the data freshness needed, what happens when there is no data, ... This would lead to leave some data out, have some edge cases that need to be discussed with further people and most likey will go back to customers saying: how do want me to calculate an average when a day is missing? type of questions.

B will have some trascripting app of the meeting, has a markdown file now, that will feed to claudecode or codex, then add a Jira pluging, create the tickets execute the model's pland and after two or three interations when nothing is failing, will mark the task as done.  

So, now imagine that a customer asks: how are you calculating an average when a day is missing? Well the reallity is that B that _doesn't don't know_! 

An important lesson here, is that in the case of A one could argue that is more valuable what A doesn't do that what it really does. What I mean by this, is that saying NO, leaving edcases out and making decisions on missleading data, is many times harder than the task itself. 

## Vicious way of working



## The 10x engineer


## Conlusion

If you've followed until this point of the article, I hope you've seen how a _way to automate_ you most tedious task can lead to you: feeling left behind and axious. If you chose to leave the _hard part_ of your job to AI, be aware that the interst is _you'll leave the highest pleasures_ to AI too. [Add the research about people linking the hard part of the job most]. And what will you be left with? Well, all the unchanlelling tasks that can't be automated such as the compulsory team meetings. But as you don't work in any of the challenges and feel completly detach to the tasks, you'll start feeling like those task and resposabilities are from someone else (the AI) [Add references to symtomps of burnout here] . With this resultion on you becoming more unhappy: about your job, and about your day to day. 

So, we've ended up with a more anxious, more burnout and unhappier version of you. It doesn't look to me that you are better off that when you started. 

To finish in with some sparkles of optimism, no, I don't think this is _the only way_ to use AI. But, I've seen more and more people fall into this trap. So next time you want to start a task with AI, ask to your self, what is the part where I'll learn and grow, and I encourage you to leave that outside of the prompt ;) 