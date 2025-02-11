---
title: Is feature engineering dead?
date: 2025-02-11
tags:
    - Feature Engineering
    - Machine Learning
    - Model Optimization
---

With all the recent boom of Large Lenguage Models (LLM's) and around decade of interest in Machine Learning (ML), I wonder where does data fall? It feels like nobody is actively talking about data curation, spacially data transformations for better modelling and more optimun models is not as cool as talking about the latest transformer architecture. 

This is a very counter intuitive trend for me. Don't get me wrong, I'm aware of how corporate and startups overload the term AI and how it has stopped being a technical term to be a new sales pitch. But besides that I wonder: We are developing more and more complex models with very sophisticated architetures, and even if yes we do have the compute power to train those, should we? 

From this refection I have two topics that come to my mind: *Is feature engineering dead ?* and should we *Make feature engineering trendy again?*

## 

### Machine Learning Systems

On the modeling side, I've seen countless "proofs of concept" that made me question what we even mean by POC these days. I've watched teams propose incredibly sophisticated architectures right from the start, or pitch trendy tech that's completely disconnected from their existing stack and capabilities. [Hidden Technical Debt in Machine Learning Systems](https://papers.nips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html) talks about the maintenace burden of this type of decisions, but we keep making them anyway.

Here's a key sign I've learned to spot after sitting through dozens of these proposals: Ask about model explainability. If the team starts shuffling in their seats and can't clearly explain why they're using a complex neural net with 100 features for something that could be solved with linear regression and PCA, you're probably looking at unnecessary complexity. I've seen this pattern repeat so many times - teams jumping straight to the most complex solution without first proving why simpler approaches wouldn't work.

A design doc can be a lifesaver here. I'm not suggesting you need to try every possible approach - that would be impractical. But documenting why you've discarded certain alternatives, even in a simple "Considered Approaches" section, helps both reviewers and future maintainers understand the decision-making process. I can't count how many times I've looked back at a complex implementation and thought "Why didn't we just use X?" only to find no trace of that discussion. A few bullet points explaining "We considered approach X but rejected it because of Y" can save hours of future head-scratching.

### State of feature engineering in the current

The complexity monster isn't just lurking in our ML components. ML systems are particularly susceptible to this because they inherit complexity from both worlds: ML and software. I've seen teams create these massively over-standardized in-house libraries that make both the service and the library weird to maintain. You end up with unnecessary boilerplate and spaghetti code that would make any developer cry at 3 AM during an incident.

{{< figure src="/images/fearture_engineering_trends.png" alt="Google ternds for: FE, ML, and LLM" >}}

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

[Add avice here]

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