---
layout: post
title: "Why I like Rust as an Engineering Leader"
subtitle: "And how it makes my job easier"
description: "Rust's compiler shifts errors left, cuts cloud compute costs, and attracts engineers who value stability. Why I advocate for Rust as an engineering leader."
excerpt: "So it's not that we should always use Rust, but I do think we should be building with Rust a lot more, and in a lot more ways. We should be expanding the vision for when we use Rust, as far more software would benefit from stability and sustainability"
date: 2026-06-30 00:00:00 -0000
# updated: 2026-02-08 12:00:00 -0000  # Uncomment when updating existing posts
categories: [engineering]
tags: [software-engineering, technical-leadership, best-practices, opinion, rust]
---

As a leader of any team there are a lot of decisions you make that you will need to live with for a long time. In engineering leadership these are often technical decisions, of which one of the biggest is the choice of programming language.

Introducing a new language into a tech-stack is not an opportunity that presents itself that often as we are often working with some kind of legacy systems and an existing team that has a certain skill set in terms of languages. Greenfields projects are not that common, and often when they happen the programming language decision can be glossed over, instead choosing whichever language is the easiest to get started with for the team.

I was fortunate enough to be in a position where I have been able to make this decision in recent years, and for a new component in our tech-stack I led our decision to use Rust.

## What is Rust?

Rust is a programming language focused on safety, speed, and reliability. Unlike languages such as Python or JavaScript, Rust catches many kinds of errors at compile time — before the software ever runs. It achieves this through its ownership model, which guarantees memory safety without needing a garbage collector. This makes it well suited for building infrastructure where stability and security matter most.

![Ferris, the crab, Rust's mascot](/assets/images/posts/2026-06-30-why-i-like-rust-as-engineering-leader/ferris.png)

## Why Rust?

The compiler. Rust is not the only language to have a compiler, but Rust's compiler gives us more guarantees than most. This is how we get the memory safety, type safety, performance and ownership guarantees.

However, it's not for those technical reasons that I like Rust, it's for what those mean for us building software with Rust.

### Costs

The efficient __performance__ of Rust in production gives us applications and servers with __lower compute costs__ and a greater ability to scale with increased load. This not only means you can build more performant software, but that software costs less in terms of cloud compute, and therefore dollars.

Compute costs can also be seen in terms of the electricity and other resources needed to power this software, whether that be in data centres or on device. In a world of increasing environmental collapse, these costs matter to me too.

### Stability

__Stability__ is also a consequence of Rust's technical strength. The stability of the software we build is important because we want to be __building new features and not fighting fires__. No one likes an emergency in production, you want production to be boring. Rust helps us __shift the errors__ we would have earlier in the development cycle by having the compiler catch these issues.

This means we don't have production systems that are crashing and causing major downtime. Of course you can still write Rust code that has errors, especially logical errors, but leaning further into Rust's type system can help us reduce these kinds of errors too.

### Maintainability

This kind of stability and reduction of errors also means that our systems are more __maintainable__. Even if we build and deploy some software and infrequently add features to it, the way that Rust code can be written allows us to make refactors and maintenance of the system much easier as we have the compiler helping us with this work, verifying that refactors and maintenance work are not destructive against our use of the type system.

### Supply chain security

You can of course use linters, tests and other tooling in your CI/CD to achieve strong correctness checks with other languages, but these are extra steps you need to add on-top of the language. The fact that a lot of this is built into Rust means that you also have more trust in the __supply chain security and stability__ for the crates (libraries) that you choose to use in your projects. This means you can take on these dependencies and feel far more confident in the code others wrote that you are relying on.

All of this is relevant to all engineers using Rust, but for engineering leaders there are even more factors to consider.

## What matters to engineering leaders

### Code reviews

For engineering leaders that review a lot of code, Rust's compiler and the guarantees we talked about above make it easier for us to __focus on the business logic in code reviews__. We've all likely had the experience of pointing out a dangling null or unhandled exception in a pull request, and whilst there is value in that, that is not what we want to be doing as engineering leaders.

This is what it looks like in Rust, where the compiler catches the null that is returned before we need to in a code review:

```rust
fn find_user(id: u64) -> Option<User> {
    // returns Some(user) or None
}

// The compiler requires both cases — no NullPointerException is possible
let user = match find_user(42) {
    Some(user) => user,
    None => return, // can't forget this, the compiler won't let you
};
```

### Best practices

I also find that the approaches and best practices we can enforce in Rust code align with __my own preferences__. The type safety and explicitness of Rust code allow us to enforce practices that make code more __readable and robust__. I have [written about](https://dylanivanbrown.github.io/blog/2023/10/18/rrrr-software-principles/) these ideas a few years ago, before I worked with Rust.

Encapsulating these best practices in the code, with the power of the language's compiler means that they are enforced through the engineers working flow, which means that the approaches you set up are taught to your engineering team __through practice, not just reading docs__.

### Mindset

Another hidden benefit of Rust is that the language's approach attracts a certain type of engineer. These are engineers with the __right mindset__ (in my opinion) for building sustainable and stable software, because it's those factors we spoke about [earlier](#why-rust) that draw these engineers to Rust.

Idiomatic Rust pushes you towards writing code that __remains stable with changes__, the type system can help us to ensure that changes we make do not break previous assumptions we had (and might have forgotten). Additionally, having to be __forward thinking about how the code will change__ is also something that aligns well with the mindset encouraged by idiomatic Rust development.

## So we should always use Rust?

No, despite all these reasons I have provided for why I like Rust as an engineering leader, there is __no tool or language that is always the best__ for everything. There are plenty of use cases where choosing another language, like Python, would be the more appropriate choice.

Sometimes the libraries you would need to build on top of are not available in Rust and you are limited by your language options, unless you have the capacity to build that yourself in Rust.

Sometimes the stability of building with Rust is not as important a factor, and you want to build with the acceptance that you are shifting development effort towards production. I think the era of "move fast and break things" has made us think this way far too often, but there are times that this is appropriate, particularly where your team would have a __learning curve to overcome__ at the same time with taking on Rust.

So it's not that we should always use Rust, but I do think we __should be building with Rust a lot more, and in a lot more ways__. We should be __expanding the vision__ for when we use Rust, as far more software would benefit from stability and sustainability.
