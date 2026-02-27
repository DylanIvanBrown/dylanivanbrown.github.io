---
layout: post
title: "Spec-Driven Development"
description: "Why spec-driven development with AI coding assistants shifts responsibility, reduces learning, and removes the joy from engineering."
excerpt: "Spec-driven development can be a great exercise in working with AI coding tools, but it robs the spec writer of critical details and most importantly the joy of building software."
date: 2025-02-27 18:00:00 -0000
categories: [engineering]
tags: [ai, coding-assistants, software-engineering, productivity, code-quality, learning, opinion]
---

So this idea of spec-driven development has become quite popular recently, based on the assumption that if we write complete specs for a problem, then the AI coding assistants can do the grunt work - just taking that and making it into code.

Whilst I think there is a lot of value in spec-driven development and this does make sense for improving the outcomes from these coding assistants, I think that it is still fundamentally flawed as a solution.

## Shifting Responsibility

The first problem with spec-driven development as a means for AI coding is that you still need to get everything fully accurate and completely understood in your spec, otherwise the tools will replicate your misunderstandings and you're the only one left to blame about it. It shifts all of the focus for getting everything right onto the human putting together this spec, and in real engineering teams this isn't really how we work.

As humans we have agency about the work that we do. When we're taking a spec from a product team or another engineering colleague, we still have to take that spec and make sure that it has the details we need. We're going to be thinking through the problem as we're working through it, and it makes the responsibility for the full product development process a group effort. Whereas with AI coding spec-driven development it feels like a much more lonely exercise.

Natural language itself is also not the best form for capturing the kinds of logic and details we need to write good software, this is why we have programming languages and mathematical notation to represent the logic that computers ultimately need.

## Learning Through Details

The second aspect of spec-driven development that can be detrimental to engineers is that it can prevent us from learning as much about what we are building.

When we're doing spec-driven development it can often be very high-level. Maybe it's easy in natural language to not have to cover all of your bases with something - all your edge cases, all of your scenarios that you need to deal with. And whilst working with an AI coding assistant can get you closer to covering all of this with the right prompt and a good bit of back-and-forth, it still doesn't really facilitate you as the engineer thinking about the details of this problem in the same way as when you write the code.

The value in working on the details of a problem as an engineer is that you get to properly understand this problem, not only what the problem is, but also how you're going about solving it. So this kind of spec-driven development where we deliver the spec once and then we let the AI tool deal with the details robs us of the deep knowledge that is fundamental if we want to build sustainable and maintainable software.

When you don't know about the details it means that the next time you need to make changes you become more reliant on the coding assistant to make the changes, and your prompt for what changes to make is less well informed because your knowledge of the solution has drifted further from how it is implemented. The tools can of course take in the context from the whole solution, but as that grows over time the quality of the model's work will degrade.

We see this with the `context rot` problem that many people are facing and have been talking about that, so I'm not gonna go into the details of that here (but let me know if you'd like me to write more about that).

This means that regardless of how much context you effectively get into the codebase through the model, there's still so much more that you're not realising by not actually getting into the weeds and tackling the problem yourself.

This spec-driven development exercise can be good for engineers to help build up understanding of what goes into creating a good spec and what questions they might need to ask a product person in order to get the right details for implementation earlier in the process, but it's not the panacea of AI-driven development that a lot of people would have you believe.

## The Joy of Engineering

The final part of this is what's also most important to us as humans, and that is the fun of it. We want to do work that we find rewarding. We don't expect our work to have the same kind of dopamine hit as playing a video game or other experiences that are purpose built for that, but when we are motivated and enjoying our work we will also produce better outcomes because it is less draining of our energy.

So if we want to actually build maintainable and sustainable software, there needs to be an element of fun in the work that we're doing. For most engineers, we didn't get into programming in order to write specs - we got into it because we enjoyed the details of writing code, and tackling problems in that way.

If we want to keep going in a job and avoid burnout, then we will want to keep writing software that we care about and that we find rewarding. I think that's something that's important to not lose sight of in this era of executives and influencers telling us we can output more lines of code with AI tools.

To make a job sustainable, it needs to be something you actually want to do every day. Whilst this is a bit of a privileged position for a lot of engineers, we have come upon these industries in these roles because we enjoy engineering.

Importantly though, "writing code is fun" might not resonate with everyone - you might be sitting out there thinking "well actually I kind of hate it, I'd rather write a spec" - but I think it's important for us to accept that there is going to be a selection bias towards engineers who do enjoy engineering, because that's probably a big reason they are in these roles.

## In closing

AI coding tools can be a really fun novelty the first few times you use them, you write a prompt and in a few minutes boom you have a working CRUD API.

It becomes a lot less fun when you try and dive in to the code and see some of the anti-patterns or verbose code that was generated. It's tempting to try and fix this with better prompts, which leads to spec docs and agents.md (or claude.md) files full of best practices.

Next thing you know you've spent the last 3 days writing documentation and you have no clue what is really going on in the codebase.

I know, I'm speaking from experience, and what I learnt is that it's so important to pick and choose how you use these tools. Extensive spec documents are not how I've found I enjoy working. I already review a lot of code as part of my role, and I don't really need the AI to generate a lot more code (often far too much) for me to review.

I've found other ways to leverage these tools that is more fun, and more productive for me personally. I will share more about what I've found works for me soon.

For now I want you to consider these aspects of engineering that I've spoken of here, and see how they measure up against your experience of spec-driven development and using AI tools. Don't let a pursuit of vain productivity metrics (like lines of code) suck all the fun out of building software, or else you will be too drained to maintain good quality software.
