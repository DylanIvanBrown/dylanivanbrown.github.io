---
layout: post
title: "Responsible use of Chat-GPT and coding assistants to boost productivity"
subtitle: "How to get more done now without hurting yourself and your team in the future"
description: "Learn when and how to use AI coding assistants like ChatGPT and GitHub Copilot responsibly. Understand the risk vs reliance relationship to boost productivity without compromising code quality."
excerpt: "Balance risk with reliance when using AI coding assistants: where you have the highest risk in your codebase, you should have the least reliance on AI-generated code."
date: 2023-08-30 12:00:00 -0000
updated: 2026-02-22 12:00:00 -0000
categories: [engineering]
tags: [ai, coding-assistants, best-practices, productivity, code-quality]
---

As developers much of our news cycle right now is flooded with tweets, articles and discussions of Large Language Models (LLMs) and how much they can accomplish. Some even postulate and prophesize that they will replace developers. This article isn't intended to debate that topic, this article is intended to inform you on how and when (in this authors opinion) you should use LLM tools (referred to from here on as coding assistants) to amplify your productivity and learning whilst not compromising on the quality of your work or introducing vulnerabilities. We will break this series into a few parts. Part 1 will cover the pitfalls to watch out for and the general guidelines to follow. In part 2 we will look at some examples of using coding assistants to help us increase our productivity.

## The Risk vs Reliance relationship

When we want to first decide if we should use an coding assistant to assist with some portion of work or generate some code we should ask ourselves two key questions:
Is the model capable of achieving this task?
Would a reliance on using the model for this task create undue risk for my application?

Answering the first question is something I hope the entirety of this series will help you to answer. The second question is the one we will now investigate.

The core of this question of risk vs reliance is not a new one in software engineering. We can look to established standards to help us find this balance. When we are deciding whether to the write some code for a function ourselves or use a package developed by an external developer, we have to answer a very similar question: Is this function key to the reliability of my system? The more key that it is, the less we would want to create a dependency on an external developer and their code. This is the essence of the risk vs reliance relationship. Once we can establish the risk level of the task or code we want to write, we can establish how much we should rely on a coding assistant to automate that task for us. To simplify this relationship, we can think of it as an inverse linear relationship, as seen in the graph below:

![An illustrative graph of the inverse linear relationship between Reliance and Risk. Reliance on LLM generated code vs the Risk of using it for that purpose in your project. As the Risk increases you should reduce the Reliance accordingly.](/assets/images/posts/2023-08-30-responsible-coding-assistant/risk-vs-reliance-graph.webp)
*Figure 1. An illustrative graph of the inverse linear relationship between Reliance and Risk. Reliance on LLM generated code vs the Risk of using it for that purpose in your project. As the Risk increases you should reduce the Reliance accordingly.*

Now that we understand the risk vs reliance relationship we can look at some other guidelines before we look at examples of using these tools in part 2.

---

## Data Privacy

A common oversight by users of Chat-GPT is inputting private user, company or personal data into their chat. We are used to thinking of our chats as being private intimate conversations between ourselves and someone else. In this case though, that someone else is an AI, and one that offers no real guarantees of privacy. With any LLM based coding assistant you need to consider what you input. It can be very easy to input some code, but forget to remove private or secure information from it first. This is a common problem that developers face when it comes to secure information like database keys or API Keys. Leaking these can cause massive harm by providing access to secure resources to malicious actors.

The leak may also not end at the LLM provider. If the data from the chat session is used to train future versions of the LLM, then this private/secure data could be reproduced to a future user, effectively making it public knowledge and compromising your system security or data privacy.

To help reduce the chance of unintentionally inputting sensitive data into the chat, we can ensure we follow some well-known best practices, and expand on them.
Store your keys and secrets in a secure way, even when prototyping or testing. Use local environment variables, secure cloud solutions (like Azure KeyVault) and whatever other tools your development environment and tech stack offers you to protect secrets. Thankfully these established best practices also serve to protect us when using coding assistants.

Don't use real user data in testing and debugging. This is something we should already be doing to comply with regulations around personal information (e.g. POPIA in South Africa and GDPR in Europe). We have to take extra care here in what data we might share in a chat with our coding assistant, perhaps when debugging a production issue or trying to understand some production data.
Don't say something in the chat you wouldn't post on a public forum. Redefine how you consider conversations with a chat assistant, treat it not as a 1-on-1 conversation, but rather as a post on a public forum, like Stack Overflow.

Use a coding assistant that provides the option to either locally host the LLM or host in a cloud environment that is under your control. This way we can ensure the data that goes into the chat is not sent outside of the domain of our control, and that it's not used for training any public models.

## Hallucinations and malicious packages

Hallucinations are a well-known problem with LLMs. If an LLM hallucinates some code that does not compile or run, then that can be quite annoying, but it's far from the most dangerous scenario.
LLMs can be particularly susceptible to hallucinating references. We've seen this in legal spaces, where entire cases are hallucinated to support an argument, which can get the lawyers involved in big trouble. In the case of generating code we can see this danger in the hallucination of packages and references. If for example some Python code is generated, and a package is imported to help with some action, that exact package name might not be correct. It might be an entirely different package to the intended one, or made up all together.

A non-existent package may waste some of your time, but of more concern is that it could be a vector for attack by malicious actors. By identifying commonly hallucinated packages, attackers have managed to successfully exploit this vulnerability already, spreading malicious packages into code bases. These packages may function as you expect, by leveraging the real package you should have used, but then add some malicious code that could steal secure data or introduce vulnerabilities into your systems.

To avoid this, you could find the packages you might need ahead of time and instruct the LLM to use those specific packages, or you could check the packages on the relevant public feed, to see if you are getting a valid and widely used package instead of a malicious one with fewer usages. Alternatively, you can exclude the import/usage statements from any generated code that you use and rely on your IDE or yourself to find the relevant packages for the generated code. Even in this case you should still confirm the packages are correct, as there could still be vectors of attack exposed by LLMs hallucinating functions.

## Different tools for different languages

Much like humans, different coding assistants will be better and worse at output in different languages. LLMs can cover a much wider variety of language in their knowledge base than humans, but their output can still be affected by the quantity and quality of the source code languages on which they are trained.
 
Take for example Starcoder, a LLM by Hugging face, StarCoder is explicit about the limitations and strengths in terms of the training data and which languages it is trained on as well as what sources of code it uses. StarCoder was fine tuned, from the StarCoderBase model, with 35B Python tokens, indicating that it should excel at Python coding assistance. It's important to know this for any given coding assistant, and you should use with caution any tool that does not give you this insight into its training data. In my personal experience I've found StarCoder to be a useful assistant, but definitely better with Python tasks than C# tasks, but this is only anecdotal. Check out the benchmarks that are out there for code generation to help you find the right model for your task.

With all generative tools it is best to generate content in a field that you are knowledgeable about, so you can more easily spot hallucinations and other issues in the output. This is also true when it comes to generating code. Whilst these tools can be useful to help you learn a new language (we will touch on this later), generating code you intend to use in a language you are knowledgeable about is preferable as it's much easier for you to analyse that code and detect stylistic and logical flaws in it.

Takeaway rules for coding assistant choice:

- Does the tool make clear it's language strengths and weakness based on it's training data and how does that apply to your need?
- Be careful when using it to generate code in a language you are not as familiar with.
- Check out the available benchmarks for finding the most appropriate model for your use case.

## Am I plagiarising?

Another ethical, and possibly legal, consideration when using any generated code is whether that code is plagiarised or not. LLMs can produce whole sections of output that are straight from their training data, and when generating code this is a concern for various reasons.

Ethically, using someone else's code, which the LLM may have obtained without explicit permission, can be quite a tricky position to be in. Knowing the source of the training data can make a huge difference here, as like with many things we consume, an ethically sourced product goes a long way to assuaging ethical concerns.

Beyond the ethical, we also have to consider the legality of the generated code. We don't want to introduce code into our code base that could cause future legal issues. For this reason, ensuring that the training data of the LLM is permissively licensed code is also important.

## Bias

LLM models trained on "all of the internet" are prone to reproduce the same biases we often see on the internet from humans. It's important to realise and understand this.
OpenAI even provide a disclaimer in their documentation about the biases that their models reproduce.

Whilst it may be easier to see this bias in natural language uses of Chat-GPT, it is important to still consider this when we choose what kind of tasks we want assistance with. We should generally avoid relying too heavily on generated code for use cases where bias can more easily creep in. For instance, if we were creating an employee system then using the LLM based assistant to generate models for a wide range of employees, it could reproduce biases that are in it's training set.

It is important to always ask ourselves if the problem we are solving has space for bias, and to address that if so, both when using LLM assistants and not. We know that humans have biases, and we need to remember that these models, trained on human output, can have them too.

## Treat all code generated as if it's written by a new colleague

When generating code, it is important to remember that this is not code you have written. Ultimately you are responsible for the code you commit, but this is not the same as code you have fully understood and written. A good rule of thumb is to treat all code generated as if it was code written by a more junior colleague who is new to the team or project. This helps you to frame the limited understanding of the model and keep the limitations in mind, whilst ensuring you keep a critical and thorough lens over the generated code.

It's also important to make your human colleagues aware of which, if any code you commit, is generated (whether fully or partially). For this I believe that it is good practice to include in your comments a note at the top of the function or class that the code was generated, and noting by which tool (ideally including version) and on which date. It might also be useful to include the prompt here. This helps your team to read this code with the same critical lens that you did before committing it, and it also means that if a later flaw is detected with a given tool (or version), it can be quickly identified which code within your codebase needs to be assessed for that vulnerability or flaw. This almost acts akin to the using/import statements we have for external packages that we use, and allows us to keep track of these external influences in our code base.

In order for us to maintain standards across our code bases we often create coding standards for our development teams. When you onboard a new developer to your team you will usually teach them these coding standards. When you are using a LLM assistant, you should ideally do the same.

We can, as part of our prompts, specify standards to follow, such as SOLID, but these won't always be followed to the same standards and interpretation you and your team might have. The best-case scenario is to train or augment the model you are using with code from your codebase. This will also help the model to be aware of functionality that you have already created, and therefore not having that duplicated in your codebase. If your code base is clean and neat, and perfectly follows your standards then this can be as easy as using that as the embedding data set, if not you might need to select for a section of code that is neat and clean, so that the model doesn't learn bad habits from your code base too.

If you have documentation that goes with your code base then this can be very useful to add to the training data set as well. This can help the model understand the code more easily through natural language. Clear comments and good naming conventions in your code will also help with this.

There are a number of tools out there that offer this functionality. Perhaps in the future we will compare them, but first let's just note some important things to consider when assessing these products.

Treat your code base as private and sensitive data. Apply the rules about what to send and when that we discussed in the Data Privacy section.
Use a model that you can control the fine tuning or training of. Ideally this is a model where the hosting is controlled so we are sure that our code is never used to train any other model or leaked beyond our team.

---

## A summary of the guidelines for using coding assistants

Coding assistants can be quite powerful in helping you build the best quality projects in an efficient way. In this article we have discussed various important considerations to keep in mind when using these tools. The productivity gains they offer are evident, but sometimes the pitfalls are not as clear when we are excited about a new technology. It's important to take the following guidelines into account, so as not to create more future work for your team than the time you save now:

- Assess the risk of using generated code for a portion of your program according to the inverse linear Risk vs Reliance relationship
- Don't share secure or private information with the assistant during your use of it. Be careful with any code you provide it
- Don't share critical proprietary code with the assistant as it could be used in future model training and replicated outside of your space. This can be mitigated with using appropriate assistants or models that allow you to control where the data goes
- Pick the right tool for the right language. Not all tools are equally proficient at each language
- Treat all generated code as if it was created by a new, more junior, member to your team
- Clearly indicate when you use generated code, so that team mates can take this into account when reviewing the code you commit
- Be careful with code generated by the assistant. Look out for hallucinated packages or references
- Use a model that has publicly declared training data and is using permissively licensed code in that training data, so that you know that any code generated won't introduce any licensing issues for your team in the future
- Be aware of the bias that the underlying LLM models can have, and look out for this in the ways you use the coding assistant

Now that we have some guidelines to go by when using LLM based coding assistants, we can look at some examples of how they can improve our productivity, and what to watch out for in those examples in part 2.
