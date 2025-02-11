---
title: "Information Retrival (Search)"
date: 2025-02-04
tags:
    - Information Retrival
---

# Information Retrival

## Why is this topic important? 

In the LLM and AI era it may look a bit odd that search (well, information retrival) is the 1st topic picked to do a deep dive. But is somehow fundamental to the new AI revolution. 

As a machine learning engineer (MLE), the one thing that shocked me most when I first read about RAG (Retrival Augmentend Generation), was that they would have the habilty to make AI systems not be outdated 🤯.

I'm aware that there is a lot of nuance to this statement, but thing about it from the prespective of the tradictional machine learning lifecycle: you gather data, preprocess it, train a model, put it in production, the model gets outdated (you need to carefully monitor for this). Now you need to start the cycle again. The promise of RAG is, the retrival will take care of giving the model the right context and the model will still have an good asnwer as long as the context is good. 

There is another angle too. If you've ever worked at an entreprise, one of the issues you'll face as an MLE is the deployment cadence. It depends on the model, but most ML models get outdated or their performance starts to suffer withing weeks (plus you want to accomodate possible traing issues) which forces you to constatly deploy new models. This is very different from the standard software development lifecyle, where in some places you may find code running for + 10 years. 

So, here I was, thinking: would RAG solve all my issues? (spoiler not at all), was search a topic worth to deep dive in? ABSOLUTELY, let's go 🤿! 

## What is "search"? 

The field that studies how to give back the most relevat documents given a query is referred to as Information Retrival (IR). Populary known as search because of of browser searchers. There are multiple appraoches to this problem, and sice this is a deep dive well talk a bit about most of them.

{{< figure src="/images/what_is_information_retrieval.png" alt="Ilustration on what is information retrieval" >}}

*A good analogy would be that information retrieval is like talking to an experienced librarian where you'd ask: "I want to know recipes with chocolate" and they'd give you "the books with the best chocolate recipes"*

### Classic Tecniques

Information retrival stared 40's and 50's with the purpose of retriving academic papers. And it wasn't until the 90's where the field exploted with comertial World Wide Web. There are three key parts that any information retrival system needs to have: indexing, query processing and matching & ranking. 

{{< figure src="/images/classic_ir_system.png" alt="Ilustration on a classic IR system" >}}

*Note that indexing is a process that only happens when new cookbooks or books arrive, while query processing and matching and ranking happen every time there is a user request*

**Indexing**: Process to make mappings between words and documents. The goal of indexing is to store the documents so retrival is quick. 

**Query processing**:  Is cleaning up search queries before looking for matches. It basically analizes the user's search tearm, handles misspelling and variations and applied boolean logic (see boolean retrival below)

**Matching and ranking**: The goal here is to select the documents that fit in the specified terms (matching) and select the most relevant ones according to a criteria (ranking).

When it comes to tequines various breakthroughs happened between 40's and the 90's:

In idenxting, we went from inverted indexes 