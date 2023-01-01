# learn `rust`

Learn `rust-lang` to build systems.

# Why? 

[Atwood's Law](https://en.wikipedia.org/wiki/Jeff_Atwood#Career) 
states:

> “_Any application that **can** be **written** in **`JavaScript`**, 
> **will** eventually **be written** in **`JavaScript`**._”

We've been there and seen the _appeal_ of JS-everywhere.
And then subsequently felt the pain of having to _debug_ and _maintain_ 
complex `JS` codebases in large teams. 

Seriously, open the DevTools of your Web Browser
and remind yourself of the "quirks" of `JS`:

![javascript-quirks](https://user-images.githubusercontent.com/194400/218910187-895842b1-9e1e-4a8f-a860-7b3346a0f6b1.png)

Many teams have opted to use `TypeScript` 
to paper over the cracks in `JS` by having static typing,
but it's a `bandaid` [on a bullet wound] at best. 🩹
Better than _nothing_ ... 
but the underlying engine still allows 
people to write un-safe code
and there are still errors discovered by "end-users"
when `TypeScript` is used. 

Even with the `TS` compiler you can still end up with 
"undefined is not a function" in your production code: 
https://stackoverflow.com/search?q=typescript+undefined+is+not+a+function

![typescript-undefined-is-not-a-function](https://user-images.githubusercontent.com/194400/218911289-528ed8a4-e619-408e-8e51-4ceee501dbaa.png)

> **Note**: we are speaking from _multiple years_ of experience 
> with writing `TypeScript` in large teams. 
> Most recently
> a `ReactNative` App for a FinTech company 
> that was written in `TS`
> and executed `TS` Lambda functions on the backend ... 
> This is fairly typical "Full Stack" these days.
> It was a nightmare to debug. 😱
> And the management answer 
> was to just throw more people at the problem. 
> There's a better way. 

Why _not_ just use a language 
that solves all of these issues
and have resulting programs 
that execute **at _least_ twice as fast**?


Eventually, _all_ code will be written in 
a **type-safe high performance programming language**
that is ***maintainable***
with the help of a 
[**_friendly_ compiler**](https://youtu.be/0rJ94rbdteE). 

We wish we made the switch sooner! ⏳


# What? 💭

Rust is a multi-paradigm, high-level, general-purpose programming language. 
Rust emphasizes performance, type safety, and concurrency.
~ https://en.wikipedia.org/wiki/Rust_(programming_language)

This is a pretty good textbook definition. 
But it doesn't tell me _anything_ about the _benefits_ to _me_! 🤷‍♂️

## What's in it for _Me_?


"_In other languages it's easy to start projects,
in `Rust` it's easy to **finish** them_" 
~ No Boilerplate "Stop Writing Rust" - https://youtu.be/Z3xPIYHKSoI

When referring to popular `Rust` projects
that haven't been updated in _years_,
Tris observed:
"_They are not abandoned, they are `done`._"

This is a breath of fresh air 
to anyone who has 
had to _maintain_ code 
in any other language.


# How? 👩‍💻

The Rust Programming Language (official book)
is the best place to start: 
https://doc.rust-lang.org


## Install

https://doc.rust-lang.org/book/ch01-01-installation.html


```sh
curl --proto '=https' --tlsv1.3 https://sh.rustup.rs -sSf | sh

```

> **Note**: as a security-conscious person I don't feel super comfortable
runnint an arbitrary script on my computer like this ...
but `rustup.rs` is the _official_ way to install `Rust`, `Cargo`, etc:
![rustup-is-official](https://user-images.githubusercontent.com/194400/216534229-29d4df72-2e63-460c-b342-fc52d18a722f.png)


https://rocket.rs
Build Web Apps With RUST (aka Intro Into Web Framework ‘Rocket’):
https://youtu.be/nJWN0wrPHRo

## Background Reading

+ Should I `Rust`, or Should I `Go` (Andrew Lader): 
https://codeburst.io/should-i-rust-or-should-i-go-59a298e00ea9
+ Go vs Rust?
https://matthias-endler.de/2017/go-vs-rust
This is a very balanced comparison.
Spoiler: 
[Mattias](https://github.com/mre) 
describes himself as a `Rust` Consultant!
+ Rust Reviewed: Is the hype justified? 🦀
https://dev.to/somedood/rust-reviewed-is-the-hype-justified-1pa1