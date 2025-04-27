---
title: "The Value of Engineers in the AI Era"
date: 2025-04-25
tags:
    - LLM
    - Developer Productivity
    - Coding Assistance
    - AI Tools
---

# The Value of Engineers in the AI Era

The name of this post started as "thoughts on Cursor" evolved into "thoughts on any AI assistant for coding," but I ended up having a more philosophical battle with myself, and that's how I came to "The Value of Engineers in the AI Era."

If you're expecting a fierce critique of these tools, this isn't your place. I definitely don't like doing repetitive work, and I see these tools as an IDEAL way to offload tasks I don't enjoy doing MYSELF. However, among software developers on the "We should use AI for coding" team, I see lots of unrealistic expectations and claims that are both contradicting and unrealistic.

## Claims

This post was triggered by two main claims. The first came from my father (who is not into programming or AI), and the second was told to me by someone in a senior leadership role in engineering:

* [**NVIDIA CEO says the future of coding as a career might already be dead in the water with the imminent prevalence of AI**](https://www.windowscentral.com/software-apps/nvidia-ceo-says-the-future-of-coding-as-a-career-might-already-be-dead)

* **These tools will allow every engineer to be a 10x engineer**

There are other articles, of course, with different views on AI. The public opinion isn't settled, and the debate is ongoing across Reddit, Medium, and other platforms. I recently came across a Forbes article, [AI And The Future Of Coding](https://www.forbes.com/sites/johnwerner/2024/01/24/ai-and-the-future-of-coding/), where John Werner argues that "AI will not replace coders; rather, coders who use AI will replace those who don't." This makes more sense to me than the doom-and-gloom predictions.

But the goal of this article is to reflect on why I still support AI-based tools for programming despite the hype, and to dig into what I think is the real value of an engineer.

## Okay, why aren't you afraid of losing your job then?

I'm not. Or not today. Maybe I should be — who knows if my manager reads this blog and deeply dislikes it ;). Jokes aside, I'm not afraid, and if I were worried about my job, I don't think it would be because of AI.

Any tech company is trying to solve a **business problem** **through tech** for customers who are willing to pay for that **service** or **product**. This statement is broad and generic, but it's the foundation of what we do.

Let's analyze what is the value proposition of an engineering department in that **business**. The goal of engineering is to create and maintain a product that solves the business need and satisfies customer expectations.

Here's the trick: **satisfies customer expectations**. Can I ask Cursor to create an app for me? Yes. Will I know what's going on in that app if a customer complains about it crashing? Probably not. Is that **what the customer expects**? I guess it depends, but I'm pretty certain my manager won't be happy about it.

### What do they pay you for?

In different engineering levels, companies, roles, and even *PROJECTS*, this can vary wildly. I've been paid for: creating machine learning solutions, building ML systems at scale, developing services to consume ML models, architecting systems, and currently scaling systems that involve ML.

But across all these roles, there are three KEY things you get paid for:

1. **Solving important problems**: If you're working on something irrelevant to the company, it doesn't matter how hard you work—your results won't matter. The Forbes article mentions that engineers who work on strategic problems create significantly more business value.

2. **Understanding business context**: Being able to translate business needs into technical solutions and vice versa. This is crucial because it ensures you're building something that actually solves the right problem.

3. **Making smart build vs. buy decisions**: Companies pay you because it makes more sense to build something in-house than to buy an existing solution. This could be due to cost, customization needs, or strategic reasons.

Notice that system design, software architecture, or even coding aren't on this list. Those are the means, the *what* they expect, but not the whys.

In his interview on [The Philosophy of Software Design](https://newsletter.pragmaticengineer.com/p/the-philosophy-of-software-design), John Ousterhout argues that software design will be even more important with AI tools than without them. I think he's right—the harder questions won't go away; if anything, they'll become more central to what we do.

### What do they not pay you for?

I personally **REALLY** hope AI can help me here. There are so many tasks where I provide 0 value but due to regulation, nature of the work, or other factors, I still need to do them:

* Writing documentation that follows a strict format
* Implementing yet another CRUD endpoint 
* Setting up the same development environment for the fifth time
* Converting between data formats (the bane of my existence)
* Writing test cases for straightforward functions
* Crafting SQL queries for simple data extraction

Before going deeper into this topic, I want to clarify that there's a **clear** tradeoff: *I'm aware I'm not learning how to do these tasks, but because I'm not interested in doing so (I think I'll only do it once, I need to do it fast, or other reasons), I opt for AI to do it for me*.

Last week, I needed to parse a weird CSV format. I could have spent an hour figuring it out, or I could ask an AI tool to do it for me. I chose the latter and got back to what I actually wanted to do—analyze the data, not parse it. Did I learn how to parse that specific CSV format? No. Do I care? Also no.

### Making smarter decisions about AI usage

When deciding whether to use AI for a task, consider both the technical complexity and the business value:

| If the task is... | And the business value is... | My approach is... |
|-------------------|------------------------------|-------------------|
| Super technical and complex | Critical to the business | Use AI to help you with research and brainstorm, but make sure to understand everything that's happening. |
| Technically simple | High business impact | Use AI to speed things up, but focus on making sure it aligns with business needs. |
| Complex technically | Not that critical | Use AI to help you learn about the complexity, but invest time in understanding the concepts. |
| Simple technically | Low business impact | Let AI handle it completely. Quick review, done. |

This approach helps you use AI where it makes sense and invest time where it matters.

## Should everyone be able to code?

This is another hot topic. My answer is YES. At least everyone who is interested. My main coding language is Python, and what I like most about it is how **easy to read** and **flexible** it is.

Not everything you code needs to be enterprise software. I use coding to track some of my expenses—a plain script against a spreadsheet. It automates stuff I need to do, and it works. I probably spent less than 20 minutes writing that script that runs weekly, about a year ago. The manual task took me about 5 minutes each time. Simple math:

```
5 mins * 2 per week * 52 weeks a year = 520 mins a year ~ 8.5 h
```

Investing 20 minutes to save 8.6 hours makes sense to me. Would it make sense if my bank offered that functionality? Absolutely! I wish they did, so I wouldn't need to maintain it!

So, just as I'm not a professional accountant but know the basics about my taxes, professional developers shouldn't fear non-developers using AI to generate code for specific needs. The Forbes article suggests that "democratizing coding through AI will likely create more technical jobs, not fewer." I'm not 100% convinced of this, but I do think it'll change the landscape in ways we haven't fully anticipated yet.

## Practical bits that have worked for me

AI is just one more tool in the toolbox. Here's what's worked for me so far:

1. **Be crystal clear about what you want**: The more precise you are, the better the results. Vague prompts lead to vague code.

2. **Use AI for the boring stuff**: Let it handle the repetitive tasks so you can focus on the interesting problems. I use it for boilerplate code all the time.

3. **Always review what it gives you**: I never, ever blindly accept AI-generated code. I've caught subtle bugs that would have been nightmares to debug later.

4. **Ask it to explain stuff**: This has been surprisingly helpful. When I don't understand a concept, having AI explain it in different ways has helped me grasp it faster.

5. **Remember it's a tool, not a replacement**: The real value is still in how you think about problems and connect solutions to business needs.

6. **Take AI breaks**: I've found it helpful to solve some problems without AI assistance to keep my skills sharp. If I relied on a calculator for all basic math, I'd eventually forget how to add.

## So what's the future look like?

Rather than worrying about whether AI will replace engineers, I'm more interested in how our roles will evolve. I'm seeing a few shifts already:

1. **More focus on why, less on how**: As AI handles more of the implementation details, the "why" questions become more important.

2. **Requirements becoming more critical**: Defining what to build becomes more valuable than writing the code itself.

3. **Business context is king**: Understanding how technology supports business goals is increasingly the differentiator.

4. **AI wrangling as a skill**: Getting good at directing AI tools is becoming a valuable skill in itself.

I'm not sure if the Forbes article is right that "the future belongs to collaborative intelligence," but I am convinced that engineering isn't disappearing—it's transforming. And honestly, I'm pretty excited about it. The parts of my job that I find most tedious are exactly the parts that AI seems best at handling.

## References & Further Reading

1. **The Philosophy of Software Design**  
   John Ousterhout interviewed by Gergely Orosz  
   [https://newsletter.pragmaticengineer.com/p/the-philosophy-of-software-design](https://newsletter.pragmaticengineer.com/p/the-philosophy-of-software-design)

2. **NVIDIA CEO on AI and Coding**  
   Windows Central  
   [https://www.windowscentral.com/software-apps/nvidia-ceo-says-the-future-of-coding-as-a-career-might-already-be-dead](https://www.windowscentral.com/software-apps/nvidia-ceo-says-the-future-of-coding-as-a-career-might-already-be-dead)

3. **AI And The Future Of Coding**  
   John Werner, Forbes  
   [https://www.forbes.com/sites/johnwerner/2024/01/24/ai-and-the-future-of-coding/](https://www.forbes.com/sites/johnwerner/2024/01/24/ai-and-the-future-of-coding/)

4. **Stack Overflow Developer Survey 2023**  
   Stack Overflow  
   [https://survey.stackoverflow.co/2023](https://survey.stackoverflow.co/2023)