---
layout: post
title: "The Confidence Problem"
subtitle: "Why uncertainty is the solution to the noise"
description: "Why do LLMs always sound so confident, even when wrong? Understanding how these models are trained gives us insight into the answer, and it's quite predictable."
excerpt: "The way that these LLMs are trained through reinforcement learning and on internet data gives us a pretty good insight into the systematic reasons that we get these kinds of outputs from these models."
date: 2026-09-04 00:00:00 -0000
# updated: 2026-02-08 12:00:00 -0000  # Uncomment when updating existing posts
categories: [meta]
tags: [ai, opinion, machine-learning, chatbots]
---

We are all inundated with confidence these days. Whether it is the confidence of AI generated text and its 3 part "_statement_, setup, **punchy definitive statement**" pattern or someone trying to break through all the noise and have their opinion heard, all we hear is confidence.

What we need is more humanity, more nuance, more uncertainty. Whether it's you or your text extruding machine, the repeated confidence makes it seem more like a performance than any actual take worth listening to.

Of course it's ironic that I'm making somewhat strong statements in this piece, but that's weeks of them boiling away in my brain spilling out into this piece, and I want to capture that.

So let's get into those thoughts.

## The confidence of models

No I'm not talking about human models, or those who think they are, who appear to have high self confidence in their appearance (aside from any of the more deep seated insecurity that these toxic industries create).

Fundamentally though the reason is the same, systems that reinforce a concept or idea and then propagate that same idea back at others.

The way that these LLMs are trained through [reinforcement learning](https://en.wikipedia.org/wiki/Reinforcement_learning) and on internet data gives us a pretty good insight into the systematic reasons that we get these kinds of outputs from these models.

Reinforcement learning means that if the companies are training on how humans interact with these tools (and we know they do with [data workers](https://www.democracynow.org/2026/8/27/data_workers)) then we should expect these models to bias towards outputs that are more likely to be accepted and responded to positively by humans.

As I [wrote previously](https://dylanivanbrown.github.io/blog/2026/03/31/the-boys-who-cried-agi/), we as humans have our own biases when we read the output of these models, and when the model outputs language that seems so confident and definitive it's no surprise that we are more likely to accept that. It's this that leads to all the "you're absolutely right" memes when we eventually realise that what was stated as "_real_" was in fact not.

You might think of this as a "_hallucination_", but I think the problem is deeper than that. We generally talk about "hallucinations" as the result of the inherent probabilistic nature of the vector mathematics at the core of LLMs, but this _confidence problem_ is a function of the training data and a clear direction of travel for these models that points to a flaw in the training methods themselves.

## The problem predates AI slop

If we are being honest though, this problem is not an entirely new problem. It's just so much more evident now that we see the same kind of "[load-bearing](https://louisabraham.github.io/load-bearing/)" vocabulary and confident statements in the slop that people post and share.

The problem is algorithmic too. It's also why social media became so divisive and toxic long before ChatGPT. You've seen this in the YouTube eras of "X person DESTROYS Y group of people" and similarly titled videos and social media posts that try to clickbait us.

These kinds of titles and styles spread _because they worked_ in the social media algorithms that were driven and reinforced with the same human biases about what we would click on and engage with. We want to see the extremes, especially when they reinforce our existing biases. This led to the algorithms feeding us more of this content, and creators creating more of this content because that's what was reinforced through the views and interactions.

The humans creating the content wanted the validation, alongside the financial gains, from making this content that would appeal in the algorithm and get views and interactions.

So when we take all this internet content that was created with years of this algorithmic bias in mind and _train models with content that skews towards this kind of confidence_ then is it any surprise that these models reflect that back to us?

## So it's unfixable?

With the current direction that these companies are going, then yes it doesn't seem like it will improve.

Could it though? Yes I think it could. With the right _curation of data sets_ for training we could try and select for content that wouldn't have this bias baked in.

From there we would need to address the reinforcement problem by looking at how the generated outputs compare with the truth, however uncertain that is, and the _long-term acceptance_ of these outputs.

By extending the range of what we consider to be good output based on its acceptance by human users, we can try to hedge against the most confident and definitive sounding solutions being accepted, only for us to later get the "you're absolutely right, I should not have ..." message we all meme online.