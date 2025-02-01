---
title: Is complexity in machine learning systems justified? 
date: 2025-01-24
tags:
    - Software Design
    - Machine Learning System Design
    - Cognitive Load
---

Machine learning (ML) systems are becoming increasingly sophisticated, and a critical question keeps me up at night: Are we building solutions that exceed our cognitive capacity to understand and maintain them?

This isn't just theoretical anxiety. The concept of [cognitive load](https://thevaluable.dev/cognitive-load-theory-software-developer/), introduced by John Sweller in 1988, tells us our working memory can only handle so much information at once. In ML and software development, this translates directly into how much mental effort it takes to understand, maintain, and operate our systems. As complexity grows, I've watched teams struggle with reduced efficiency, higher error rates, and increasingly painful development cycles.

## Sources of Cognitive Load in Modern Systems

### Machine Learning Systems

On the modeling side, I've seen countless "proofs of concept" that made me question what we even mean by POC these days. I've watched teams propose incredibly sophisticated architectures right from the start, or pitch trendy tech that's completely disconnected from their existing stack and capabilities. [Hidden Technical Debt in Machine Learning Systems](https://papers.nips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html) talks about the maintenace burden of this type of decisions, but we keep making them anyway.

Here's a key sign I've learned to spot after sitting through dozens of these proposals: Ask about model explainability. If the team starts shuffling in their seats and can't clearly explain why they're using a complex neural net with 100 features for something that could be solved with linear regression and PCA, you're probably looking at unnecessary complexity. I've seen this pattern repeat so many times - teams jumping straight to the most complex solution without first proving why simpler approaches wouldn't work.

A design doc can be a lifesaver here. I'm not suggesting you need to try every possible approach - that would be impractical. But documenting why you've discarded certain alternatives, even in a simple "Considered Approaches" section, helps both reviewers and future maintainers understand the decision-making process. I can't count how many times I've looked back at a complex implementation and thought "Why didn't we just use X?" only to find no trace of that discussion. A few bullet points explaining "We considered approach X but rejected it because of Y" can save hours of future head-scratching.

### Software Design

The complexity monster isn't just lurking in our ML components. ML systems are particularly susceptible to this because they inherit complexity from both worlds: ML and software. I've seen teams create these massively over-standardized in-house libraries that make both the service and the library weird to maintain. You end up with unnecessary boilerplate and spaghetti code that would make any developer cry at 3 AM during an incident.

{{< figure src="/images/code_complexity.png" alt="Code Complexity in one image" >}}

Software engineering also falls in the "latest shiniest tech trap". One curious pattern I keep seeing is the overly optimistic scaling expectations. You hear things like "Let's use technology X because when we hit Y million users..." How about we first make sure anyone wants to use this feature? Following agile methodology, wouldn't it make more sense to face scaling problems when we actually have them?

If you are looking for a detailed reference [A Philosophy of Software Design](https://www.youtube.com/watch?v=bmSAYlu0NcY) includes over-engineered architecture patterns, unnecessary abstraction layers, complex dependency graphs, and inadequate documentation.

## When Complexity Becomes Problematic

I've watched many engineers follow patterns or technologies simply because "that's what management wanted" or "because we need to implement technology X." The typical prioritization matrix I've seen focuses on impact vs. time, which is fine, but it often ignores the long-term maintenance burden and complexity trade-offs.

For instance, I recently saw a project where the team prioritized using a trendy new framework, but completely overlooked how it would affect their ability to debug production issues six months down the line. The functionality looked great in demos, but the maintenance costs were crushing.

## Managing Organized Complexity

While some complexity is inevitable, it needs to earn its keep. Read more on [Donald Norman's work on complexity](https://www.amazon.com/Living-Complexity-Donald-Norman/dp/0262014866). Before implementing any solution, I've learned to ask two crucial questions:

* "Could I ship this with half the complexity and still solve the core problem?"

* "If I go with the simpler version now, how hard would it be to scale later?"

The tough part? Being brutally honest with those answers. Your future self (or the poor soul who inherits your code) will thank you.

## Practical Advice for Practitioners

After years of cleaning up overcomplicated systems (including my own), here's what I've learned:

1. Start simple and prove you need complexity. I've seen too many projects fail not because the technology wasn't sophisticated enough, but because it was too sophisticated to maintain.

2. Remember: the most elegant solution isn't the one that shows off your ML chops - it's the one that can be understood by the team at 3 AM when something goes wrong.

3. Question the build vs. buy decision carefully. Sometimes starting with a third-party API is the right choice, but make sure you're not overengineering a solution just because you can.

4. Keep your eye on the maintenance costs. The initial development is just the tip of the iceberg - the real costs come from long-term maintenance and operations.

Keep it as simple as you can, then add complexity only when you can prove you need it. Your sanity (and your team's) depends on it.

For a deeper dive into managing cognitive load in software development, check out this excellent [GitHub repository on cognitive load](https://github.com/zakirullin/cognitive-load).

## References & Further Reading

1. **Cognitive Load Theory for Software Development**  
  [https://thevaluable.dev/cognitive-load-theory-software-developer/](https://thevaluable.dev/cognitive-load-theory-software-developer/)

2. **Hidden Technical Debt in Machine Learning Systems**  
  D. Sculley et al., 2015  
  [https://papers.nips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html](https://papers.nips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html)

3. **A Philosophy of Software Design**  
  Talk by John Ousterhout  
  [https://www.youtube.com/watch?v=bmSAYlu0NcY](https://www.youtube.com/watch?v=bmSAYlu0NcY)

4. **Living with Complexity**  
  Donald Norman, MIT Press  
  [https://www.amazon.com/Living-Complexity-Donald-Norman/dp/0262014866](https://www.amazon.com/Living-Complexity-Donald-Norman/dp/0262014866)

5. **Managing Cognitive Load in Software Development**  
  Community Resource  
  [https://github.com/zakirullin/cognitive-load](https://github.com/zakirullin/cognitive-load)