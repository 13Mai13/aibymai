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

But there's a type of problem that doesn't go away just because an API exists. It's the kind of problem **where the answer isn't "right" or "wrong" in an obvious way**, where you're tuning something based on numbers you've half-trusted, and where the only honest response to **"did this get better?"** is “probably yes, I added a few more checks.”

That type is exactly where data science earns its keep. Let me show you what it looks like from the inside with an example. 

## A chatbot, a car, and a sofa

Say you're building a chatbot for IKEA. Most of it is unremarkable — answer questions, find products, handle returns. But there's one feature with real complexity: a customer gives you their car model, picks a sofa, and the chatbot tells them whether it'll actually fit in the trunk.

Under the hood this isn't the LLM's job. It's a secondary model — something that takes car dimensions and furniture dimensions and outputs a fit decision. You don't have measurements for every car and every sofa that's ever existed, so you do what people in this position always do: you start with your top sellers. The most popular cars, the most popular sofas, a known set of ground-truth fits, and a model trained to extrapolate from there.

It mostly works. Then someone tries a Volvo V60 with a corner sofa, the model says it fits, it doesn't, and you've got a support ticket and a return shipment to show for it.

So you fix it. You add a rule for estate cars like the V60. A week later, a Volkswagen Polo fails the same way — a much smaller car, but the model never learned why size alone isn't the whole story — so you add a rule for compact hatchbacks. Then a modular sofa fails for the opposite reason: it's a flat-pack, it would have fit fine, but the model flagged it as too big because it didn't account for the chaise longue piece being optional and the customer hadn't selected it. So you add a check for modular configurations. Each fix is reasonable on its own. None of them tell you whether the model, as a whole, is getting better — only that you've patched the specific failure someone happened to notice.

This is the trap: you can keep doing this forever. There's no natural endpoint where you've "found all the edge cases," because the input space is enormous and your visibility into it is whatever support tickets happen to surface. You're not improving the model. You're playing whack-a-mole with a model you can't see the shape of.

## What a scientist would do

Here's the question that actually matters, and it's not "how do I catch the next failure." It's: if I tune this model, **how do I know if it's better — not just better at the cases I personally tested?**

This sounds like a hard, new problem because it's wearing an LLM-shaped costume. It isn't new. It's the problem data science, and statistics before it, solved decades ago: you don't trust a change because it feels right or because the cases you checked look fine. **You trust it because you set up a test that could have proven you wrong, and it didn't.**

**Train, validation, test — and why the order matters**. The standard discipline is to split your data three ways. You train the model on one chunk, you tune it — your V60 rule, your Polo rule, your modular-furniture check — against a second chunk it hasn't memorized, and you only touch the third chunk once, at the very end, to report how it actually performs. The validation set is where you're allowed to fail and adjust. **The test set is where failing means something.**

The discipline that's easy to skip is keeping those sets honest. If your "fix" for the V60 problem comes from looking at the exact V60 that failed and then checking whether your change helps on a set that included that exact car — congratulations, **you've contaminated your own evaluation**. Train-test contamination happens when **information from the test set accidentally leaks into the training process**, producing high accuracy that doesn't reflect how the model performs on genuinely unseen data. It's a quiet failure mode because the **metric goes up. It just stops meaning anything.**

This isn't a hypothetical risk that only applies to a  car-and-sofa example toy. It's the same failure currently undermining how the entire field evaluates LLMs. Lexical obfuscation techniques — shuffling multiple-choice options, substituting synonyms, applying reversible ciphers — try to prevent models from relying on memorization, but modern LLMs often see through these transformations because they were trained on the obfuscated formats too. The contamination got bad enough, and accumulated for long enough, that benchmarks like MMLU, HumanEval, HellaSwag, and the original GSM8K have effectively been retired — all of them sit in the 90s for top models, and none of them produces a useful ranking signal for frontier work anymore. The field's response wasn't to stop caring about evaluation. It was to build harder benchmarks with cleaner splits. Same problem, same solution, just a newer set of acronyms.

**Overfitting is the same disease wearing a different name**. Your V60-rule, Polo-rule, modular-furniture-rule model isn't failing because the rules are wrong. It's failing because each rule was reverse-engineered from a single failure and validated against nothing. That's overfitting in its most literal form: a model — or in this case, a pile of patches around a model — that has learned the specific cases in front of you instead of the underlying pattern. The fix isn't a smarter patch. It's putting every patch through the same validation set, every time, before you decide it earned its place.

**Online testing is the same idea, with real customers instead of held-out rows**. Once you trust your offline numbers, the next question is whether the improvement survives contact with reality — and that's what A/B testing is for. The foundation of any experiment is comparison: a control group experiences the current version, a treatment group is exposed to the change, and you compare their behavior to measure the impact. For the IKEA chatbot, that might mean shipping the V60 rule update to a fraction of sessions and comparing the rate of "fits" being contradicted by actual returns. As you can imagine, due to its online component this is a more expensive failure, but still better than pushing a the worsened model to all the production traffic. 

The trap here isn't technical, it's a matter of restraint. It's tempting to build a whole experimentation platform before you've earned the need for one — sequential testing, multi-armed bandits, stratified sampling by region and car class. Most of that is solving a problem you don't have yet. **The simplest test you can run and actually interpret correctly beats a sophisticated one you build incorrectly**. Start with a plain control-versus-treatment split, a single metric you'd be willing to be wrong about in public, and move to anything fancier only once that stops being enough.

## The part that doesn't get easier

None of this — train/validation/test discipline, contamination checks, A/B tests — makes the underlying problem easy. Evaluating an LLM, or a system built around one, stays genuinely hard, because so much of what these systems do doesn't reduce to a single right answer the way "does the sofa fit" does. That's a real difficulty, and I don't want to pretend it away.

But "this is hard to evaluate" and "I'm not going to evaluate it" are different sentences, and it's worth noticing how easily the second one hides inside the first. Adding one more test to catch the next failure feels like rigor. It isn't, if you can't say whether your last ten changes made things better or just made things different. **Not knowing the impact of a change — not even a rough estimate — is functionally the same as not having made a change at all**. You can't justify the time spent on something you can't show moved a number you trust.

## Closing the loop

Go back to the chatbot. The version of this team that survives long enough to actually trust their car-fit model isn't the one that ships the most patches. It's the one that, at some point, stopped treating every failure as a new rule to write and started treating it as a question about the validation set: does this rule survive contact with data it's never seen? Does the number I'm reporting still mean what I think it means?

That question is old. It predates neural networks, predates the term "data science" itself, and it's not going anywhere just because the model in front of you now writes in full sentences. The interface changed. The discipline required to trust what comes out of it didn't.

## References

1. **Data leakage and train-test contamination** — [Data leakage in machine learning explained](https://www.educative.io/blog/what-is-data-leakage-in-machine-learning), Educative
2. **Train/validation/test splits in practice** — [Train/Validation/Test Splits and Data Leakage in Practice](https://gtracademy.org/train-validation-test-splits-and-data-leakage-in-practice/), GTR Academy
3. **Benchmark contamination retiring major LLM benchmarks** — [What Is a Contaminated LLM? Detection, Famous Cases](https://llm-stats.com/blog/research/what-is-a-contaminated-llm)
4. **Lexical obfuscation and benchmark resistance** — [LLM Benchmark Datasets Should Be Contamination-Resistant](https://arxiv.org/html/2605.19999v1), arXiv
5. **LiveBench, a contamination-limited benchmark** — [LiveBench: A Challenging, Contamination-Limited LLM Benchmark](https://openreview.net/forum?id=sKYHBTAxVa), ICLR 2025
6. **Control and treatment groups in experiment design** — [Experimental Design Principles, A/B Testing in Big Tech](https://oboe.com/learn/ab-testing-in-big-tech-ewi45f/experimental-design-principles-1)



