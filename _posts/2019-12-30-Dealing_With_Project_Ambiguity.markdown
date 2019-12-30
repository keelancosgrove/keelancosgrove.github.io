---
layout: post
title:  "Dealing with Project Ambiguity"
date:   2019-12-30 13:46:56 -0500
categories: jekyll update
---
Even during my first year as a full time software engineer, I saw the technical leaders around me wrestling with problems with no clear solution. I wasn't a primary decision maker at the time, but still encountered the following examples:

* How do we debug a failing system when all previous subject matter experts have left the company?
* How do we balance feature development and operational improvements on an underresourced team?
* Should we start development on an ambitious project when we don't yet have data to show it would have a clear benefit (nor do we even know what metric to evaluate against!)?

Hard problems have no obvious answer. They often have no preceding examples to follow, which is how I completed my initial projects - by essentially copying the principles of what's worked before, i.e. "If it ain't broke, don't fix it." If given a problem that has already been solved, the DRY principle rightfully recommends reusing an existing solution. But what happens if none are readily available?

Over the last three years, I've started to dabble in ambiguity and have gained the following insights. Here is a rough list of pointers for how to approach a tough project. Each is a large enough subject to write an entire book about. Fortunately I'm not that wise, so all I can offer is a paragraph or two:

**1. Identify the set of key metrics (or KPIs)**

If it's not already clear, this is the first question to answer. What is the exact customer benefit we're trying to achieve, and do we already have an existing mechanism to measure it? For example, in S3 I've seen several eternally open backlog tasks to refactor particularly messy code bases. The reason these were never prioritized is because no one offered a concrete measure of why it's worth it. "The code is messy" or "It's not adhering to XYZ design principle" is not sufficient. Why would management care about that? Rather, a superior statement would be "It took our new hire Dio 2 weeks to add a simple feature flag to this legacy system, despite requiring no major changes to the business logic" or "We estimate that having a refactored code base would save up to 2 engineering months on this upcoming feature request project, requiring several database schema modifications". The key is identifying metrics such as "time to introduce a simple change" or "time to deploy schema change".

**2. Estimate the benefit the project will deliver in the key metrics**

The second step is to take the fastest possible approach to demonstrate benefit in the identified metrics. Approaches include proof from a similar project on a different system, or an estimation from a heuristic can suffice (only when the workflow is really simple). Often a more heavy-handed approach is needed. A prototype is one of the strongest ways to prove that a project is worth investing in. Additionally, it helps identify implementation challenges which were not obvious during planning. It is the minimal implementation to demonstrate observable customer benefit.

In the past I've sometimes hestitated to begin prototyping, and self-reflection as to why exposed gaps in the team's development process. For example, how can I quickly try changes in legacy code bases written in low level languages, with little documentation? This raises the possibility of an interpreter (or REPL) to simulate the system written in a high level language. Or how can I estimate the impact at production scale if all our tests are designed to be run on a small developer box? This raises the possibility of automated load testing environments. It's also important to ask if the team itself encourages experimentation, at the expense of delivering results in the short term.

**3. Develop a project design and execution plan**

This is the design phase. While messy, the prototype offers part of an implementation plan. The other parts include consulting with other team members about the results from steps 1-2 and the plan. Moreover, it's important that a design is not just an abstract solution. It needs to identify concrete action items and ideally estimations for each. The best designs I've seen break projects apart into milestones, each with an estimation of the engineering effort and expected customer benefit. I've previously suffered from being a perfectionist when it comes to scheduling design reviews, constantly refining the document or asking new questions. I would procrastinate reviewing with the team because of perceived technical flaws in my design. One insight I've had is that there's no way to have all the answers, and that criticism is something that should not be feared. More concretely, I prefer to schedule a review time with the team when I have a rough idea of how to tackle the project, even if there are still open questions. This forces me to time box my investigation, openly identify the unknowns in the design review, and draft action items to find answers to the important problems.

One of my past managers advised me to include several approaches for each technical decision, including their advantages and drawbacks. This can be useful when there are multiple choices with no clear winner. If it's a two way door decision, then the choice is not as important. But otherwise it's an indicator that more investigation is needed. For decision points with a clear winner, I don't see much benefit in listing inferior approaches.

**4. Implement**

Yay coding! If the above steps went smoothly, so should this.

That's a high level overview of how to tackle ambiguous projects. Still, I find it helpful to walk myself through this process when given any problem with undefined scope.

This is the first career oriented post, not all of my posts will pertain to software development. I'm still debating posting more about specific systems/engineering design principles, or about general project management/engineering advice. Right now, I'm more concerned about developing my leadership skills and a 5-10 year career plan rather than learning about a specific technical subject, so there will likely be more of the latter.