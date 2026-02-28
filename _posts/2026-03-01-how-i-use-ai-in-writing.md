---
layout: post
title: "How I use AI in my writing"
subtitle: "Or more importantly how I don't use AI"
description: "An experience-based step-by-step guide on using AI tools to build momentum and clean up your writing, without losing your voice or generating AI slop"
excerpt: "From transcribing my thoughts whilst washing dishes to a published post, here's how I use AI tools in my writing without generating AI slop."
date: 2026-03-01 01:18:00 -0000
# updated: 2026-02-08 12:00:00 -0000  # Uncomment when updating existing posts
categories: [meta]  # Choose: general, engineering, meta, personal, etc.
tags: [ai, productivity, tutorial, learning]  # Choose 3-5 tags in kebab-case from /tags/ page
---

Let's be clear, this isn't a hype piece about AI tools being so great. I don't want AI to write things for me, I don't want my voice to get drowned out by AI slop, or for people looking at my writing to think I've just AI generated what they are reading.

I'm not writing to produce X amount of content in Y amount of time, to keep up some algorithmic cadence and build impressions and bait conversations or outrage. I write to share my thoughts, to give myself space to strengthen and mould those thoughts, and to be an expression of myself, so I'm pretty careful about how I use AI in my writing process.

## What my process looks like

Ideas for pieces I want to write often come when I'm in the middle of something else. I'll realise, "wow this is a frustrating experience with this tool", or "Ahah! That's how I can do that better" or "that's why we do it that way, now it makes sense" or in this case "well maybe this is something others can learn from my experience".

Often I'm in the middle of something else when this thought happens so I'll write down bullet points in a note or a markdown file.

The problem is that list grows, and the number of pieces I actually properly write out and publish doesn't keep up at anywhere near that rate. In fact, the longer the list grows the more overwhelming it can be to look at that list and pick something to write out.

## What hasn't worked for me

So in the past I have thought, let's take one of those ideas with all their bullet points and try to get an AI tool to write them out in nice proper sentences and then I can go from there.

Whilst this does help me to make progress on a piece, I've found that it often turns the piece into generic-looking AI slop, and walking back from that place is quite difficult. When we see the AI generated written out version of our ideas (in code or natural language), it can be difficult to go from that initial place to something that looks like what we would naturally do ourselves.

Change is difficult, and AI generated text is naturally resistant to change. These tools and models are trained on what we accept, and what we don't, so naturally they are optimised for us accepting the output. So when you start with the AI slop version, even if it's all your own ideas, it can be quite difficult to walk it back to a representation that reflects your voice.

That being said, not all hope is lost. I think I've found a way that AI tools can be helpful, at least to me.

## What has worked

With a recent piece I wrote on [Spec-driven Development](https://dylanivanbrown.github.io/blog/2026/02/27/spec-driven-development/), I took a different path to using these tools, and I found that helpful.

### Step 1: Capturing my voice

The initial thrust for this piece came whilst I was washing some dishes one day. I'm a perpetual multitasker, I'm all about making my time as efficient as possible. So in order to make washing dishes efficient I decided to try something I had been wanting to try to help my writing, and something I had toyed with a bit before, and that is transcribing my thoughts for a first draft.

I had tried a few transcription tools before, but in this case I needed something on my phone, so I decided to just transcribe a note using the built-in Apple transcription tool.

The first draft it transcribed was rambly and sometimes repetitive, it had long run-on sentences (Apple's transcription seems pretty bad at finding when a sentence ends), and quite a few obvious transcription mistakes, but it captured my voice (literally) and represented how I would talk about this concept and the construction of the piece that was in my head.

### Step 2: My voice to a readable text

A few days later when I decided I needed to write something for an upcoming writing club meeting, I decided to take a look at the transcribed text and see if I could turn that into something that was actually readable.

In this process I used OpenCode, with Claude Sonnet/Opus models, to help me clean up what had been transcribed. Importantly though I instructed them to not change the content of the piece. Instead I first focused on the format of the piece, instructing the model to break my transcription up into different ideas, simply adding spacing to the work.

![First pass cleanup of the format and run-on sentences of the transcription](/assets/images/posts/2026-03-01-how-i-use-ai-in-writing/step-2-formatting.png)

Next I tackled some of the obvious transcription errors. There were quite a few, some quite funny (see image below).

![Some of the funny transcription errors from the Apple transcription and the AI fixes for them](/assets/images/posts/2026-03-01-how-i-use-ai-in-writing/transcription-errors-with-prompt.png)

This helped me to have something that felt authentic to my voice, and that I could actually parse for improvement without being confused by the transcription, or losing the idea with the formatting. One more quick round of formatting and flow fixes and I was ready for the next step.

### Step 3: Good old-fashioned rewriting

This step was probably the longest one, but also probably the most important. Now that I had something that captured the ideas I wanted to discuss, the voice I wanted to speak about them in, and was in a readable format, I could begin writing it all again.

There is no magic to this step. It was simply a case of tackling each line one at a time. Some needed heavier edits and rewriting than others. Slowly I worked my way through the whole piece, feeling pretty happy with the progress I was making.

Importantly, I was expecting this to take time. I was not expecting a miracle because I was using AI, and I wasn't willing to sacrifice my voice for a quicker rewrite by the AI model.

The important takeaway from this step is not a "_here's one neat trick to double your output_", but more of a "_avoid this trap if you want your output to be your own_" kind of lesson.

### Step 4: AI the editor

I'm sure you've heard of people using AI as an "editor" for their writing. That is what I wanted to do in this step, but once again I instructed it to retain the style and content of what I had written.

![Step 4, post human rewrite edits](/assets/images/posts/2026-03-01-how-i-use-ai-in-writing/step-4-post-rewrite-edits.png)

The tool came back with some pretty helpful suggestions, as you can see above. I decided to work through these all myself, and see if I agree with the edits in the full context of the text. I did end up making almost all of them, but I didn't want the model to overreach and make the edits itself.

I prompted again for more and got back some new ones, some of which seemed to be either hallucinations or mistaken context from an old version of the file. Once again I made them myself.

### Step 5: AI the marketer

Something I personally struggle with is Search Engine Optimisation (SEO). I know why it's valuable, and I have some idea how it works, but I struggle to actually do it for myself.

In previous work on my writing for the blog I had the AI tool generate an SEO checklist and help with SEO on posts. This time I could point to that SEO checklist and get the tool to help me with the SEO of my new post.

As with other pieces I had written, I wasn't a big fan of the excerpts and descriptions it generates. I often found them to vastly overstate the statements I was making, overemphasise the wrong elements of what I was talking about (especially when it comes to AI), or just generally produce AI slop smelling text.

Interestingly, in this process I also asked it to update the date of the piece, as it had been a day or two since I initially dated and started writing it, and it wrongly set the year as `2025`. This mistake was quite a sneaky one, as I only realised it after publish, when the post was in what seemed like the wrong chronological order on the home page.

![Incorrect year change by the model from 2026 to 2025 when asked to update the date of the post](/assets/images/posts/2026-03-01-how-i-use-ai-in-writing/date-error.png)

The other aspects of the SEO optimisation I found fairly helpful, and after a couple iterations of the description I finally had a piece I was happy with.

## /exit

Whilst this process is not the only way I write (I wrote this piece quite differently), I think it has been helpful as a way for me to use AI to build momentum with my writing, and get some initial feedback in areas I struggle with, without losing my voice in the process.

I hope that this, or at least some parts of this process can be useful to you too.
