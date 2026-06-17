---
title: You Didn't Fix the Model. You Memorized the Failure.
subtitle: Evaluation didn't get easier when the model got smarter — it just got easier to skip
date: 2026-06-17
tags:
    - Draft
    - Machine Learning
    - Evaluation
    - LLMs
    - Data Science
    - MLOps
---

A quick note before we start: this isn't an argument against using LLMs to solve real problems. It's an argument against using them as a substitute for thinking about whether the problem got solved.

## The disappearing model

There used to be a clear line between "this needs a model" and "this is just logic." Lately that line has mostly dissolved into a single move: **call an LLM**. Classify the ticket, summarize the call, route the request, write the SQL — an API call handles all of it, and for a large share of these tasks, that's genuinely fine. The model is good enough, the stakes are low enough, and nobody needs a confusion matrix to know that a summary is roughly right.

But there's a category of problem that doesn't go away just because an API exists. It's the kind of problem **where the answer isn't "right" or "wrong" in an obvious way**, where you're tuning something based on numbers you've half-trusted, and where the only honest response to **"did this get better?"** is "I think so, probably, I added a few more checks."

That category is exactly where data science earns its keep. Let me show you what it looks like from the inside with an example. 

