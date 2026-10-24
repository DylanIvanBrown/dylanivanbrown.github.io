---
layout: post
title: "Why LLMs must write human readable code"
subtitle: "Even if you don't care to read it"
description: "We often hear that the end game for LLM coding is low level machine language. This fundamentally misunderstands how LLMs work and the human data behind them."
excerpt: "The people saying this are fantasising, understanding how LLMs work makes this obvious."
date: 2026-10-23 00:00:00 -0000
# updated: 2026-02-08 12:00:00 -0000  # Uncomment when updating existing posts
categories: [engineering]  # Choose: general, engineering, meta, personal, etc.
tags: [ai, coding-assistants, software-engineering, opinion]  # Choose 3-5 tags in kebab-case from /tags/ page
---

We have been hearing for months, maybe even years now, that eventually "AI" will stop writing human readable code.

The people saying this are fantasizing, understanding how LLMs work makes this obvious.

## The misunderstanding of progression

Those espousing this view seem to believe that future progress for LLM based coding will move along some kind of linear or exponential progression based on where we have gotten to now.

That reminds me of this classic meme that lampoons this idea.

![The classic baby meme where a father holds his son and states that he has doubled in weight in 3 months and at this rate will weigh 7.5 tons by age 10. Demonstrating the ridiculousness of this kind of projection](/assets/images/posts/2026-10-23-why-llms-must-write-human-readable-code/classic_baby_growth_meme.webp)

The reason that both of these projections are silly is the same. There is a fundamental misunderstanding about how we got here.

## How LLMs produce code

Even though I'm a big fan of [readable code](https://dylanivanbrown.github.io/blog/2023/10/18/rrrr-software-principles/), my issue with this statement isn't rooted in the quality of the resulting code base, but in the way that LLMs work.

LLMs are next token prediction machines, that means that they are predicting the likely next token given all the tokens in their training set.

So one of the reasons they have been able to predict next tokens for programming languages is _because of all the human written code they have trained on_.

That means to get the same quality of generation in some vague future machine language, or even an existing machine language you would need a _massive training set_ in that language. Not just that, you would also need the right data in a human readable language alongside that to know what machine language tokens to generate from the human language tokens!

This just doesn't exist. To think this is to misunderstand the _immense scale_ of the data sets that have been scraped from _decades of human contributions_ to the internet.

Unsurprisingly the internet is also going to skew towards those who are interested in computers and coding, so the internet data will also skew heavily in that direction.

This combined with the verifiability of code through testing and running it is what makes these LLM powered tools able to output code that works.

Working code is not the only part that matters in software development though, but that's something for a [different piece](https://dylanivanbrown.github.io/blog/2026/06/13/more-code-review-is-bad/).
