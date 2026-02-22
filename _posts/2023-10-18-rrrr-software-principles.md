---
layout: post
title: "The Pirate (RRRR) Design principles for software"
subtitle: "My personal view on how to write good and clean code"
description: "Four practical design principles for writing maintainable code that reduces bugs, improves collaboration, and helps teams scale. Learn the RRRR approach."
excerpt: "The RRRR (Pirate) principles for software design: a practical framework for writing readable, reusable, maintainable code with reduced responsibility."
date: 2023-10-18 12:00:00 -0000
updated: 2026-02-08 12:00:00 -0000
categories: [engineering]
tags: [design, engineering, best-practices]
---

These design principles are not new, they are built upon my influences and experiences throughout my career so far (10+ years total, 5+ as a team lead, CTO and Engineering Manager). Thank you to all the great developers I have learnt from, as well as all those who have published work on coding design principles.

The intention of this piece is to express the design principles that I try to live by. This serves many reasons, the first of which is to keep myself accountable to these design principles. It's far too easy as the leader of a development team to teach and enforce design principles, but not hold yourself to the same principles. (Side note: this can be even more difficult if developers in your team don't feel they can make suggestions and that their feedback is valued. Being a dictator will not make you better, learn from everyone, no matter their level of experience).

The second reason for this piece is to serve as a reference for developers, in the teams I work with and the wider audience that might want to consider these principles when building software.

Please note that when I use terms like "clean code" or "good code" this is my interpretation of what this means. Ultimately what is most important is what works for your team.

To make these principles easier to remember, I've broken them down into the 4Rs, R⁴ or the pirate principles.

## Table of Contents
- [Readable](#readable)
- [Reusable](#reusable)
- [Reduce Responsibility](#reduce-responsibility)
- [Robust](#robust)
- [In Summary](#in-summary)

### Readable

Readability is an often undervalued aspect of clean code. If you want to have code that is maintainable you need to make sure that you can easily return to it after a time away. Remembering what a section of code does is difficult, especially as a code base grows over time, but if it's written with readability front of mind then it should be easy to pick up, or figure out if don't remember the details about it. As someone with ADHD I personally find this even more important, as my ability to understand is much greater than my ability to remember.

Readable code is also incredibly important in collaboration. Whilst readability is important even if you are just building something yourself, the impacts of readable code are far greater when someone else also has to read your code. Readable code is more likely to have issues identified in Pull Requests, it will be far easier for your teammates to spot issues when your code is very easily understood by them reading the PR. This makes it easier to identify when you might be breaking any other principles (in this article or of your own/team), or if there are scenarios not covered by your documentation.

Readable code is also more easily maintained by a teammate (reducing siloing). It's not only you who has to return to code you wrote months or years ago. The larger your team and the bigger your codebase the more important readability becomes for team maintenance. A good rule of thumb is that someone should be able to understand the code without any input from you (not from commit messages or accompanying documentation). This could be especially important as people move in and out of teams. Losing a developer on a team can be a real brain drain, if the code is too complex and not easily understood by the remaining team members then this is amplified. Readable code makes it easier to offboard and onboard developers to the team. Within a bigger organisation, that has multiple teams, this can also help the organisation to retain the talented developers they have, as developers can much more easily switch teams when they need a new challenge, without it being a drain on them and their teammates.

Readability can come in multiple forms. Class, object, function and variable naming are obvious examples I'm sure we have all struggled with. Formatting of code, as well as structure of a project can also make code more readable. Reducing the cognitive load on the reader is an important factor to consider writing readable code. Using terms that internal to your organisational memory, or references within your code (naming or structure) that require the reader to know something else are good examples of increasing cognitive load and therefore making less readable code.

In short, I believe that readable code produces less bugs, makes maintenance easier and helps organisations retain developers and grow development teams. Readability is one of the key aspects of the R⁴ design principles.

### Reusable

Reusability is a much more well discussed aspect of clean code. We have all likely encountered this design principle in other terms or forms. The reason I put this principle second in the list is that I believe reusability is the second most important aspect of these design principles.
Reusable code helps us to reduce the scope of future development work by ensuring that we already have code that we can reuse in other applications or functions that require the same functionality as our previously written code.
Reusability can take the form of internal shared libraries of helpers or models (published through something like Nuget or Npm) that enable you to not have to repeat logic that is common in your application or across microservices. This has obvious benefits in terms of time to build, as well as ease of maintenance.

Keeping reusability in mind can also help you to consider readability and the other 4R design principles. Reusable code should be generic, but focused enough that it is easily readable. Thinking about whether a piece of code you are writing should be reusable can help you to make naming easier as well as helping you reduce the responsibility of the code (more on this next).
Considering how you distribute your reusable code can also help you to tackle problems of maintainability of microservices or multi-client models by forcing you to face some of the key problems up front.

Whilst we would all like to have the foresight to perfectly predict when code will be reused in the future, if we had this ability we would all be making far more money in other professions. Considering reusability as a priority can help you to build this skill (in terms of development, not poker). More often though we will get this wrong first time, and that's important to accept and acknowledge. Having reusability as a key design principle when reviewing a teammate's code is a great way to help others get this right more often. Accepting when something previously built needs to be made reusable can help us to actively refactor legacy code, keeping it alive and making our systems more maintainable.

Don't overdo reusability though, making everything reusable can also slow you down and hinder your progress, and possibly even make your code a jumbled mess of generic terms that is difficult to read and understand.

Reusability is a difficult concept to master. Too much can slow you down, too little to can bloat your code and make it difficult to maintain and collaborate. Considering this aspect of the pirate principles is no easy task, but an important one to writing cleaner code in my humble opinion.

### Reduce Responsibility

Reducing the responsibility of a piece of code often goes by other terms like separation of concerns, or single responsibility. These terms don't fit my 4R naming convention, and I think can be a little difficult to understand (read: readable) or too strict in their application.

Considering how we can reduce the responsibility of some code that we are writing is far more realistic than expecting everything we write to have a single responsibility. Keeping this factor in mind when we write code can also help us to make code more reusable and readable as we distil it's responsibility to the lowest reasonable factor.
To reduce the responsibility of some code we are writing we should consider:
What are the key goals of this function/class/object?
What are the limits that we can expect this function/class/object to reasonably have? These could be things like integration details for a service we are consuming or the implementation of a fuzzy logic algorithm.
How can we reduce the responsibilities of our code to make it more reusable and readable?

Asking these questions of ourselves when we write code can help us to reduce the responsibility as much as is reasonably possible.

Code with reduced responsibility can also be more easily maintained. For example, having a repository that handles integration for the storage provider as well as additional system logic means that when we want to update or replace the storage provider we are using we also have to replicate the other system logic.
Reduce responsibility is a principle that is much fuzzier than some of its predecessors, this is necessary to help address the fuzziness of software development. Reduce responsibility as much as is reasonable. That's the key axiom to live by from this principle.

### Robust

Code needs to be well tested and able to handle a variety of situations (scale, hosting etc). We all want to write perfectly robust code, but we all (usually) hate writing unit and integration tests for our code.

Including this principle as the 4th in our list is intentional. Code that is readable, with reduced responsibility and increased reusability is easier to test, and maintain. If we have some code with as little responsibility as possible that we are reusing across multiple parts of our application then we can be much more assured of its robustness, without having to write more tests each time we want to use the functionality of the code. Readable code is also easier to understand and therefore find the edge cases in, making it easier for our test cases to cover them. Readable code also makes it easier for out teammates to identify any untested aspects of our code in a PR.

Robust code goes beyond just writing unit tests though. Robustness is a factor in design too. When we design systems we also want them to be robust to changes. What happens if Google graveyards your favourite service that you were using, or a better service is introduced? Robust code should also be robust to changes. Concepts like Dependency Injection and Dependency Inversion can help us to write code that is easier to write unit tests for, and easier to replace in the future, without making future changes introduce brittleness in parts of our application.

Robust code might seem like a simple principle at first, but when inspected further we can see that it's important to consider for various reasons in our design, and it helps to bring together aspects of all the other principles of our 4R system.

## In Summary

If you have gotten this far you may have noticed that I broke some of my own principles in this writing. I've tried to make a set of design principles that is easier to read and remember by utilising alliteration of the R in each principle, but I've not been consistent about how I refer to these principles. I've used 4Rs, R⁴ and the pirate principles as names for this group of principles. Let's use this issue to highlight all of our principles in action.
Readable?

- Being inconsistent in how I have referred to the group of principles adds cognitive load to the reader, which makes the article less readable.
- R4 looks nice on paper, but is difficult to communicate verbally. I had to look up how to say this, and the term I liked most for "to the power of 4" was "hypercubed", but the issue is there were many different ways to verbally communicate this, making it quite confusing if two people are both not aware of the same ways.
- Pirate principles is catchy, but it relies on the understanding of a joke (RRRR) which requires prior knowledge and a common sense of humor (juvenile humor in this case)
Reusable?
- Clearly, I have not made the name for these principles reusable, as I have used 3 totally different names throughout the article.
Reduce Responsbility?
- Pirate principles has two responsibilities, making the principles memorable and making the reader laugh. It could be argued that these two principles align, and that it's easier to remember the principles because of the joke, but we do have to ask if we cannot reduce the responsibility of the name further.
Robust?
- If the reader does not understand the joke of the pirate principles name then it fails our basic test of communicating the principles.
- Using numbered terms like 4R or R4 ties us to exactly 4 principles, which means that if we want to update the list of principles in the future we would also have to change the name, which could cause confusion. This is counterproductive to making the principles robust to change.

If you have found this helpful, please help me out and let's work on a name for these principles that is readable to a wider audience than I'm able to conjure in my head. Please reach out to me on twitter/X @DylanBrown_Dev or send me a connect request with your naming suggestions on LinkedIn.

If there is enough interest then perhaps we can open source this design principles article and take some PRs with name suggestions and changes. Let me know if you want to contribute in that way.

Thank you for your time. I hope you find the design principles and approach that are best suited to your team. These are just my personal principles, and may not work for everyone.