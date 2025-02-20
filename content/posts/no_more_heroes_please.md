---
title: No more heroes please, let's talk about hero culture
date: 2025-02-20
tags:
    - Software Development
    - Culture
    - Team Dynamics
---

I used to say that the only software development method I've seen successfully work is: **Incident driven development**. That means that if there is an incident it's due to A; then we all stop everything that we are doing to go fix A and the person who coded A or has most context about A solves it. We have a hero!!!

But, one sec, why did A happen at first place? *By the time you ask this everyone has left the meeting/channel and you are on your own*

# What is hero culture? 

Well, an image is better than words: 

{{< figure src="/images/hero_culture.png" alt="Hero culture meme" >}}

A definition I've liked is from [Google's Site Reliablity Engineering's presentation](https://sre.google/resources/practices-and-processes/no-heroes/): When there's a systemic problem or gap in a system and an individual decides to fill that gap.

# Is it a problem?

Many people may read this and think: well, that's not a bad thing. Someone with context solved the problem, what is the harm. The issue is not what happened, but rather how frequently it happens and the patterns it creates.

Let's consider two analogies:

1. In machine learning, overfitting occurs when a model performs exceptionally well on training data but fails to generalize to new situations. Similarly, relying on heroes might solve immediate problems, but fails to address underlying systemic issues.

2. In business metrics, focusing solely on KPIs like customer satisfaction scores might incentivize quick fixes rather than addressing root causes. A support hero might resolve tickets quickly earning praise, while the underlying product issues remain unaddressed.

## The "Hidden" costs of Hero Culture

1.  Knowledge Silos: When heroes consistently step in to save the day, they become the sole repositories of critical knowledge. This creates dangerous single points of failure in organizations. As discussed in [Team Topologies](https://www.amazon.es/Team-Topologies-Organizing-Business-Technology/dp/1942788819) this anti-pattern severely limits an organization's ability to scale and respond to change.

2. Burnout Risk: Heroes often work longer hours, take on more stress and feel pressured to always be available. This is unsustainable and leads to burnout. Research by [Understanding Hero Culture in Agile Teams](https://unconsciousagile.com/2023/11/18/hero-culture.html) shows that teams with strong hero cultures experience 50% higher burnout rates than those with more distributed responsibility patterns.

3. Reduced Team Growth: Other team members might not develop the skills and knowledge they need because they rely on the hero to handle difficult situations.

4. Technical Debt Accumulation: Quick fixes by heroes often prioritize immediate solutions over long-term maintainability, leading to increased technical debt.

"Hidden" because in every organization I've worked with that follows this pattern, there’s always a group of overlooked individuals discussing it —often loudly— yet management chooses to ignore it in favor of quick wins.

The problems with these costs, is that nobody wants to pay the interest that they carry: slowing down development until tech debt is in a better shape, reduce team growth rate so onboarding doesn't take 6 months, ...

## Practical Advice for Practitioners

I often hear phrases about YOU being the owner of YOUR career and therefore the progress lies on YOU. While I agree with this statement at first, context matters significantly and the devil is in the details. I've seen people who don't do much self-promotion get stuck in their careers, while others who do too much self-promotion and too little work get promoted.

My personal take is that an engineer has two main responsibilities:

1. Solve the right problem: Identify and address root causes rather than symptoms

2. Solve it in the right way: Create sustainable, documented and maintainable solutions

Hero culture often compromises both of these responsibilities by:

* Prioritizing quick fixes over proper solutions

* Reinforcing knowledge silos instead of promoting knowledge sharing

* Valuing individual heroics over team collaboration and growth

As Hendrich points out in [We Don't Need Another Hero: The Hero Anti-Pattern](https://medium.com/@lucas.hendrich/we-dont-need-another-hero-or-the-hero-anti-pattern-771d42b1b99c), these compromises often create a self-reinforcing cycle where quick fixes lead to more incidents, which demands more heroes.

### Identifying Hero Culture

Just as there are code smells in software development, there are signs that indicate a hero culture is taking root. While every company has essential team members with deep knowledge or long tenure, watch for these warning signs:

* Regular "emergency" situations that only specific individuals can handle

* Lack of documented processes and knowledge sharing

* Praise and recognition primarily focused on crisis management

* Team members feeling unable to take vacation or disconnect

* Resistance to implementing systematic improvements

* Recurring incidents without root cause analysis

## References & Further Reading

## References & Further Reading

1. **No Heroes: Site Reliability Engineering Practices**  
  Google SRE Team  
  [https://sre.google/resources/practices-and-processes/no-heroes/](https://sre.google/resources/practices-and-processes/no-heroes/)

2. **Understanding Hero Culture in Agile Teams**  
  Unconscious Agile, 2023  
  [https://unconsciousagile.com/2023/11/18/hero-culture.html](https://unconsciousagile.com/2023/11/18/hero-culture.html)

3. **We Don't Need Another Hero: The Hero Anti-Pattern**  
  Lucas Hendrich  
  [https://medium.com/@lucas.hendrich/we-dont-need-another-hero-or-the-hero-anti-pattern-771d42b1b99c](https://medium.com/@lucas.hendrich/we-dont-need-another-hero-or-the-hero-anti-pattern-771d42b1b99c)

4. **Team Topologies: Organizing Business and Technology Teams for Fast Flow**  
  Matthew Skelton & Manuel Pais  
  [https://www.amazon.es/Team-Topologies-Organizing-Business-Technology/dp/1942788819](https://www.amazon.es/Team-Topologies-Organizing-Business-Technology/dp/1942788819)

5. **The Phoenix Project: A Novel About IT, DevOps, and Helping Your Business Win**  
  Gene Kim, Kevin Behr & George Spafford  
  [https://www.amazon.com/Phoenix-Project-DevOps-Helping-Business/dp/0988262592](https://www.amazon.com/Phoenix-Project-DevOps-Helping-Business/dp/0988262592)