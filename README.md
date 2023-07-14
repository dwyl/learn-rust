# learn `rust`

Learn `rust-lang` to build systems.

# Why use Rust? 

## Blazingly Fast
Rust does not use garbage collector for memory management, and this means that you do not need to manually manage memory! 
You can see some benchmarks to compare Rust with C and other languages in [this post, for exemple](https://benchmarksgame-team.pages.debian.net/benchmarksgame/fastest/rust.html)

## Most Loved Language!

According to Stackoverflow's 2022 Developer Survey, [Rust is on its seventh year as the most loved language](https://survey.stackoverflow.co/2022/#most-loved-dreaded-and-wanted-language-want) with 87% of developers saying they want to continue using it. Rust was the most wanted language too!

## Memory Safety
Rust is a blazingly fast, memory safe, and concurrent programming language that runs without garbage collector, and how Rust does it?

Rust uses Ownership models to ensure memory safety. The ownership model is a set of rules that the compiler checks at compile time. The rules are:
- Each value in Rust has an owner.
- There can only be one owner at a time.
- When the owner goes out of scope, the value will be dropped. 

Ownership is a new concept for many programmers, it does take some time to get used to. The good news is that the more experienced you become with Rust and the rules of the ownership system, the easier you’ll find it to naturally develop code that is safe and efficient. Keep at it!

You can see the power of the ownership model in some cases. You can read how this is useful and how discord uses rust speed without garbage collector in their [blog post](https://blog.discord.com/why-discord-is-switching-from-go-to-rust-a190bbca2b1f).

## Cargo
When you code in other compiled languages like C you have to compile the program, insert a name and run, like you would do with the Rust Compiler:
```sh
$ rustc hello.rs
$ ./hello
Hello, world!
```
It will be boring to do this every time you want to run your program. Furthermore, most non-trivial programs will likely have dependencies on external libraries, and will therefore also depend transetivily on their dependecies. We can avoid the manual tedium involved by using the rust Package Manager.

Cargo is the rust packager manager. Cargo aims to do the following:
- Introduces two metadata files with various bits of package information.
- Fetches and builds your package’s dependencies.
- Invokes rustc or another build tool with the correct parameters to build your package.
- Introduces conventions to make working with Rust packages easier.

You can use cargo not only to build your own projects, but also to download and build other people’s projects. Cargo is the build tool that Rustaceans use most often, and Cargo’s conventions make it easy to use other Rustaceans’ code as well.

```sh
$ cargo run
    Compiling hello v0.1.0 (file:///path/to/hello)
     Finished dev [unoptimized + debuginfo] target(s) in 0.27s
      Running `target/debug/hello`
```
This simple commands runs and compiles the program. It also creates a `Cargo.lock` file that contains the exact versions of the dependencies that were used to build the program. This is important because it means that the next time you build the program, Cargo will use the same versions of the dependencies that it used the last time. This is important because it means that the next time you build the program, Cargo will use the same versions of the dependencies that it used the last time.

These command runs in the default binary project. You can also create a library project with the `--lib` flag:
```sh
$ cargo new hello --lib
```
This will create a `src/lib.rs` file instead of a `src/main.rs` file. The `src/lib.rs` file is the crate root of a library crate, and the `src/main.rs` file is the crate root of a binary crate.

Cargo turns your life easier by providing a lot of useful commands. You can use `cargo build` to compile your project without running it. You can use `cargo check` to check if your project compiles without actually compiling it. You can use `cargo doc` to generate the documentation for your project. You can use `cargo test` to run the automated tests that are in your project. You can use `cargo bench` to run the benchmarks that are in your project. You can use `cargo update` to update the dependencies of your project. And many others! If you want to know more about cargo, you can check the [cargo book](https://doc.rust-lang.org/cargo/index.html)

## And more...

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

## Concepts
Rust has many concepts that are not present in other languages but you need to get your hands dirty to understand them. 
Here some of them:
<img width="786" alt="image" src="https://user-images.githubusercontent.com/39351332/219899585-015ef7d1-730d-4e94-996d-a44127db75bf.png">
Exercism is a great place to start learning Rust, they won't take your hands and show you how to solve the exercises but they will give you the base concepts and you will have to figure out how to use them. 
For me personally, it was the best way to learn Rust.

## Books
Rust has books for almost everything, from the basics to the most advanced concepts.

I will leave some books that you will find useful:
  - [The Rust Programming Language](https://doc.rust-lang.org/book/title-page.html)
  - [Beta version of the new book, with more examples and detailed concepts](https://rust-book.cs.brown.edu/)
  - [Async Rust](https://book.async.rs/)
  - [Web Assembly in Rust](https://rustwasm.github.io/docs/book/)
  - [Performance book](https://nnethercote.github.io/perf-book/introduction.html)


## Installing

https://doc.rust-lang.org/book/ch01-01-installation.html


```sh
curl --proto '=https' --tlsv1.3 https://sh.rustup.rs -sSf | sh

```

> **Note**: as a security-conscious person I don't feel super comfortable
runnint an arbitrary script on my computer like this ...
but `rustup.rs` is the _official_ way to install `Rust`, `Cargo`, etc:
![rustup-is-official](https://user-images.githubusercontent.com/194400/216534229-29d4df72-2e63-460c-b342-fc52d18a722f.png)


# Communities:
- [Rust Brasil Telegram](https://t.me/rustlangbr)
- [Rust Devz Telegram](https://t.me/rustdevs)
- [Rust En Telegram](https://t.me/RustTalk)

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
https://rocket.rs
- Build Web Apps With RUST (aka Intro Into Web Framework ‘Rocket’):
https://youtu.be/nJWN0wrPHRo
