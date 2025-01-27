---
title: Is complexity in machine learning systems justified? 
date: 2025-01-24
tags:
    - Software Design
    - Machine Learning System Design
    - Cognitive Load
---


Machine learning systems are becoming increasingly sophisticated, and a critical question emerges: Is the growing complexity of these systems truly justified, or are we building solutions that exceed our cognitive capacity to understand and maintain them?

The concept of [cognitive load](https://thevaluable.dev/cognitive-load-theory-software-developer/), introduced by John Sweller in 1988, suggests that our working memory can only handle a limited amount of information simultaneously. In machine learning and software development, this cognitive load refers to the mental effort required to understand, maintain, and operate systems. As systems grow in complexity, this load increases, potentially leading to reduced efficiency, higher error rates, and increased development time.

## Sources of Cognitive Load in Modern Systems

### Machine Learning Systems

Modern deep learning architectures like GPT-4 or PaLM, which contain billions of parameters, introduce significant cognitive load through complex model architectures with numerous hyperparameters, intricate data preprocessing pipelines, multiple model ensembles, and difficult-to-interpret model behaviors.

### Software Design

The complexity isn't limited to ML components. As detailed in [A Philosophy of Software Design](https://www.youtube.com/watch?v=bmSAYlu0NcY), common sources include over-engineered architecture patterns, unnecessary abstraction layers, complex dependency graphs, and inadequate documentation.

## When Complexity Becomes Problematic

### Anti-patterns in Machine Learning

Consider implementing a deep learning model for a simple classification task that could be solved with basic statistical methods. For example, using a transformer model to categorize customer feedback when a simple keyword-based approach would suffice. As noted in [Hidden Technical Debt in Machine Learning Systems](https://papers.nips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html), such decisions can lead to unnecessary maintenance burden.

### Software Engineering Pitfalls

Creating a microservices architecture for a small application that could be effectively managed as a monolith exemplifies unnecessary complexity. This introduces overhead in deployment, monitoring, and maintenance while providing little benefit for the scale of the project.

## Managing Organized Complexity

While some complexity is inevitable in modern systems, it should be organized and justified. [Donald Norman's work on complexity](https://www.amazon.com/Living-Complexity-Donald-Norman/dp/0262014866) suggests that systems can be complex but structured in comprehensible ways. This means that each layer of complexity should add measurable value, systems should be modular and well-documented, components should be testable and maintainable, and the architecture should scale with business needs.

## Practical Advice for Practitioners

Before implementing the latest trends in modeling or the shiniest architecture, remember that approximately 80% of software costs come from maintenance and operations. An elegant solution is one that you understand top to bottom and are fully aware of how it works.

When designing your next system, ask yourself two crucial questions:

1. What is the minimum piece of software + model that would allow me to ship this functionality?
2. If I ship that minimal version, how much effort would improvements require?

Be honest with these answers. If you can solve the problem in a simpler way and follow an iterative approach, your initial design might be introducing unnecessary complexity.

For a deeper dive into managing cognitive load in software development, check out this excellent [GitHub repository on cognitive load](https://github.com/zakirullin/cognitive-load).