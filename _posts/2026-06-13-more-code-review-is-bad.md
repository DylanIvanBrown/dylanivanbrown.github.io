---
layout: post
title: "More code review is bad"
subtitle: "How generated code is degenerating our codebases"
description: "AI generates code faster than we can review it. Why more code review degrades codebases, drains reviewer capacity, and how teams can do it well."
excerpt: "AI tools generate code faster than humans can meaningfully review it. Here's why that degrades our codebases, and what engineering leaders and contributors can do about it."
date: 2026-06-13 17:00:00 -0000
updated: 2026-06-16 16:00:00 -0000  # Uncomment when updating existing posts
categories: [engineering]
tags: [ai, coding-assistants, code-quality, engineering-management, opinion]
---

This piece is something I have been wanting to write for some time. Now as we start to see some more push back against AI tools in Software Engineering, particularly in terms of their costs, this may be seen as a point that is too late to the discussion, yet it's not a point I have seen discussed enough.

Whilst this piece is also going to focus primarily on code generation and review, a lot of the same points apply to other types of [knowledge work and document creation](https://dylanivanbrown.github.io/blog/2026/02/28/how-i-use-ai-in-writing/).

## Code review is important

We know from years of studying good software engineering practices that code review is a very important part of writing quality code.

Research show us that metrics around code reviews tell us a lot about the quality of work by an engineering team as well as the time required for onboarding. Code review is how we make sure that the code that enters our codebases is readable and will make sense to the entire engineering team that will be maintaining this codebase over time.

In a [2018 study of code review practices at Google](https://research.google/pubs/modern-code-review-a-case-study-at-google/) it was said by the person who introduced code review at Google that:

> the main impetus behind the introduction of code review was to force developers to write code that other developers could understand; this was deemed important since code must act as a teacher for future developers.

and they also went on to say:

> the foremost reason for introducing code review at Google was to improve code understandability and maintainability

This research eventually concludes with the finding that code review is important, and that engineers find it to be important to them. One key aspect of that is that the code reviews are kept small and manageable.

With this current trend of AI tool generated output, including vast quantities of code, we are told that the key to getting good results with these tools is to review the outputs ourselves, that the humans in the loop are the key to making these tools effective. This would make sense with our established best practices around code review, but ...

These tools are generating output at a rate that quality review cannot keep up with. We have seen [some research](https://www.faros.ai/blog/ai-software-engineering) showing average PR size increases of 154%. The fervour to generate more and more does not stop, including many proponents extolling the virtues of how many lines of code these tools have generated for them or their companies in a short amount of time.

This completely flies in the face of the research and best practices we have established around code review in software engineering.

## Code review consumes energy differently

Even if we were to accept that the new normal for engineering teams is to be performing _more_ code reviews of _larger_ changes generated with, or by, AI tools that would still make for a worse outcome because code review is tiring and the amount of code to review is overwhelming.

From my experience, and I'm sure you might have felt similar, there is a very different capacity and energy that we have for creative tasks and review/management tasks. Writing code is a creative task, where you work through the problem step by step, uncovering new problems and making small decisions to solve these problems along the way. This process allows us to build up slowly to the solution we arrive at when we submit a code review.

Reviewing someone else's code means we have to unpack these decisions to understand how they arrived at this solution. Well written code that is self documenting, can make this easier, but regardless of the quality this is a different kind of mental process to writing code yourself.

The process of review is therefore often a more expensive process cognitively than creation. This means that even if we can generate more code to review with these tools, our team's capacity for review is not the same as their capacity for creation. You cannot simply replace their time spent creating with time spent reviewing and expect the same quality. This holds true for time spent reviewing generated code before the code review stage by engineers too.

## Human bias against change

Another important consideration when it comes to a shift to more review than creation is that we do not really treat these two processes the same as humans.

We have a lot of biases as humans that have been studied for years. One of these is the [status quo bias](https://en.wikipedia.org/wiki/Status_quo_bias) which results in us having a preference for maintaining the current state of something. This bias is much more prevalent when we are reviewing already written code, rather than writing that code ourselves.

When reading generated code ourselves before a code review we are also narrowing the vision for solutions to the problem, as we are much more likely to be biased towards this first solution provided by the tool, which will (by design of these models) be an average of solutions to these kinds of problems, and often not the best solution for our unique version of this kind of problem.

We've all seen that when code review processes fail it can often be because the reviewers slap on a "LGTM" (Looks Good to Me) or are too reluctant to ask questions or challenge any decisions made in the code.

Combine all of this with our lack of deeper understanding of the code, due to not working through the problem and solution ourselves, and we are going to be far more likely to accept generated code even if it is wrong or buggy.

Further add to this the previously discussed human review capacity constraints and verbose code production of these tools and we start to just become rubber stamps for the code generated by these models, not truly any kind of human in the loop.

## How to do this well

Whilst you might come to the conclusion from this piece so far that we should not use AI tools in coding, or that I am personally opposed to using them, I don't actually think that is true.

What I do believe is that these tools can be a force multiplier for good and bad processes and engineers. If your review process already looked like lots of "LGTM" rubber stamping of reviews then introducing more reviews thanks to AI tool generated code is certainly going to make things worse.

However if you are able to build a good code review process and culture with human to human reviews, you are in a much more likely position to reap some benefits from these tools. It is not likely you will see the fabled 10x increase in your lines of code or number of code reviews, but that's also not a realistic goal to aim for, and probably not going to lead to better outcomes if you believe in what we have discussed today.

With my role crossing both Engineering leadership and direct code contributions I am going to split my advice up below based on the role.

### Advice for Engineering Leaders

Don't push your teams to increase the amount of code they are outputting. We know this is a __vanity metric__ that is only going to come back to bite you and your teams. Focus instead on output and quality, which are far more difficult to measure.

Listen to your teams on where __they find value__, and where they want to try out these tools, and where it causes them more friction than is useful.

Make time for, and encourage your teams to bring the __standards and best practices__ from the team's own brains into __documentation__. This helps new contributors to projects as well as AI coding tools to have a clearer idea of what guidelines their output should follow. For neither is this a silver bullet, it can only reduce the risks, not eliminate them entirely.

Make space for your teams to __create systems__ that allow these tools to be better controlled and __more closely match your standards and best practices__. This is not only in the form of documentation, but also using automated tools like linters, or in some languages (like Rust), leveraging the compiler and what we can enforce with type safety.

Encourage your teams to share openly their successes and best ways of working with these tools, but even more importantly their __failures and the pitfalls they have encountered__. Some of these will be specific to your code bases and your domain, so sharing them with the others working in that domain are important. Files like `AGENTS.md` or `CLAUDE.md` are a good place to put "correction rules" for these tools, but it's also important that your teams understand these pitfalls themselves and don't rely on the models to work against their design and lean away from the average solution, that is not the best solution for you and your problems.

### Advice for Code Contributors

For those directly contributing to the code bases and reviews there is some overlap with the above advice for Engineering Leaders.

Putting in place the right __systems and documentation__ to try and bring generated code closer in __style and best practices__ to what you and your team would produce is a helpful step towards using these tools responsibly. Make sure you advocate for time to do this kind of work, especially before it is too late in the process and your actual code has drifted too far from your desired style and best practices because of AI generated contributions.

The technical decisions you make, both in terms of language and libraries as well as details within that implementation (like the types you define) are an important way to force generated code to adhere with important logical requirements. Having two `string` types for `Name` and `Surname`, for example, makes it far easier for humans and AI tools to mix up these values, or misuse them. Instead having distinct `Name` and `Surname` types can allow for better enforcement of the business logic around the use of these values.

Linting for all languages is also an important tool. __Updating your linting checks__ in your CI and making sure these run before code reviews happen (and making sure the AI tools run these in their process), to enforce the best practices and styling choices you decide on as a team is an important way to have these enforced in a way that doesn't consume your, or your colleagues capacity reviewing the code.

In these above ways the crux of what we are doing is trying to create ways to __protect our reviewing capacity__ by enforcing that these other details are reviewed and enforced as automatically as possible and feedback is given to the AI tooling to bring it in line with these guidelines.

Another way that anybody creating with AI can improve the quality of their output, and better maintain their understanding of what is produced, is to __start the first draft yourself__. I've written before about why [letting AI lead from a spec](https://dylanivanbrown.github.io/blog/2026/02/27/spec-driven-development/) shifts too much away from you. This could mean writing some pseudocode or code with a lot of `TODO`s and mocks and letting that structure and approach be defined by you. Using an AI tool to then expand on that (fill in `TODO`s etc) means that understanding how it has gone from step 1, to step 10 is much less of a cognitive load as you had a better idea of where you thought it was going, and if it veers away from that then you might not be as biased against pushing back on that output.

## Keep it fun

One important aspect of this that I haven't yet covered, but is particularly important to me as a person with ADHD, is that code review isn't as fun as writing code. I've not met many engineers who find code reviews more fun than writing code, that's not what drew most of us to this kind of work.

I have learnt through myself, that __what is stimulating is what is motivating__. A challenge I can problem solve my way through; getting stuck into the details of the task; learning new knowledge through deeper understanding and experience are aspects of software engineering that I find fun. It is important that we __protect the fun in our work__ if we want to create sustainable working environments for ourselves and our teams.

## So now what?

The takeaway here is not to avoid using AI tools altogether, but to properly understand the pitfalls and traps that we can fall into, especially when chasing vanity metrics. It's also critically important to not just understand these tools, but understand ourselves and our colleagues as humans, with all of our biases and constraints. Understanding all of that will help you and your teams to make much more effective use of AI tools, but it probably won't 10x productivity - but that was never a realistic goal to begin with.

## SEO Checklist

Before publishing, ensure you've completed:

- [ ] **Title** is descriptive and under 60 characters
- [ ] **Description** added (155-160 chars, includes key searchable terms)
- [ ] **Excerpt** added (1-2 sentences, captures key takeaway)
- [ ] **3-5 relevant tags** selected from the tag reference at `/tags/`
- [ ] All tags are in **kebab-case** format
- [ ] Proper **heading structure** (use H2 `##` for main sections, H3 `###` for subsections)
- [ ] At least **1 internal link** to another post (if applicable)
- [ ] **Images have descriptive alt text** (if applicable)
- [ ] Read through for **typos and clarity**
- [ ] **Preview locally**: `bundle exec jekyll serve --drafts`
