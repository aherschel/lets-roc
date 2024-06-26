# Getting Started

## Why Roc 

Roc is an FP language in the vein of Haskell/Elm, there it is still a **very young** language, still pre-alpha.

That said, I'm really drawn to the language for a few reasons.

1. The `platform` concept seems interesting, offloading a decent chunk of what might in the STDLIB to purpose-built (and modifiable) units is something I haven't seen. The initial implication seems to be the ability to embed your Roc program in different platforms, or deploy to different targets, but I also wonder if it means you could use it for building DSLs for different libraries with it. For example I really like working with the AWS CDK as a platform or abstraction (warts and all), but would we be able to use Roc to have a fully type-safe language for simplified cloud apps?
2. The reasonably small language is highly appealing. I haven't used Golang extensively, but as somebody coming from the JVM which has seen language features get added for so many years, it's nice to have a small number of ways to get things done, even if it's verbose.
3. The type system seems understandable in a way that I'm still having trouble wrapping my brain around the Rust type system (for example). As somebody coming from Typesript, writing complicated type declarations and full code in the type system is not something I want to do, so if there's a better way, I'm game.
The type system seems understandable in a way that I'm still having trouble wrapping my brain around the Rust type system (for example). As somebody coming from Typesript, writing complicated type declarations and full code in the type system is not something I want to do, so if there's a better way, I'm game.
The type system seems understandable in a way that I'm still having trouble wrapping my brain around the Rust type system (for example). As somebody coming from Typesript, writing complicated type declarations and full code in the type system is not something I want to do, so if there's a better way, I'm game.
The type system seems understandable in a way that I'm still having trouble wrapping my brain around the Rust type system (for example). As somebody coming from Typesript, writing complicated type declarations and full code in the type system is not something I want to do, so if there's a better way, I'm game.
The type system seems understandable in a way that I'm still having trouble wrapping my brain around the Rust type system (for example). As somebody coming from Typesript, writing complicated type declarations and full code in the type system is not something I want to do, so if there's a better way, I'm game.
4. This one is personal, but I just had a kid, and I'm off on paternity, using the spare cycles I have when I'm just holding him and feeding him to bone up on some of the languages I've been meaning to learn. Primarily Go (for work), and Rust (to get past the absolute beginner level). I've been working through a few books each in those languages, and the 'Writing Rust CLI programs' book has been a fairly gentle intro, while still giving material problems, so I'd like to take a similar approach to Roc, and document how that goes. Implementing echo/cat/count/uniq/find/etc.

## Installing

To start, as mentioned in the overview, installation is not super straightforward yet, at least it wasn't for me.

I had to install from source following the instructions [online](https://www.roc-lang.org/install) since I'm running linux, and I ran into a few hiccups where my laptop crashed close to the end of the build. I'm honestly not sure if this was an issue with my machine, or something else related to the cargo build, but I retried a few times from the top and eventually it worked.Maybe my cargo cache was consuming too much RAM 🤷.

I'll eventually explore this a bit more, but as mentioned earlier, I'm less concerned with polishing my setup, and more concerned with learning the language, and forming some opinions before sinking more time into that.

As recommended in the `installing` page on the Roc site, I initially experimented with Zed as the editor, but similarly had to build from source, and ran into some odd behavior depending on how I ran the editor, and looked into Vscode and vim. Vscode similarly seems to crash like nobody's business on my machine, and because I'm not sure if my laptop is slowly dying or not, I've just moved back to vim.

### (Neo)Vim Setup

I'm using Neovim with NVChad, and TBH it's not my daily driver for work or anything so I'm not a pro, that said I'm using [roc.vim](https://github.com/ChrisWellsWood/roc.vim) alongside a custom formatter to run `roc format` via [null-ls](https://github.com/jose-elias-alvarez/null-ls.nvim), as well as installing the `roc` tree-sitter plugin via `:TSInstall roc`

So far this setup is fine for what I'm doing, though it seems roc format maybe doesn't always run. I haven't spent too much time looking into whether that's true enough, but to reiterate, this is good enough for me, for now. If this is something that I continue past a few weeks, I'll look into sharpening my tools a bit more.

The commit where I added roc configuration to vim can be found [here](https://github.com/aherschel/nvim-config/commit/f3bc3876bf414170d132817b495ebee250010c2f).

Okay, so now we're set up, and can run `roc dev/test/run/build` from the command line, and have an editor running with nice syntax highlighting, some docs/completion/highlighting included via the roc-language-server, and access to the docs, so we can get started with a shakedown program.

## External Material

Note: there are useful docs, tutorials, and videos online. I've found them helpful, and also somewhat lacking, but usually scrubbing across them will help you understand the language a bit better.

* [Roc official Tutorial](https://www.roc-lang.org/tutorial) Read through this first, it's super useful, and is basically the whirlwind tour of the language.
* [Introduction to Roc Programming Language by Richard Feldman](https://youtu.be/7R204VUlzGc?si=DJIs5ZrTPjjF4jYF) there are quite a few talks and presentations from Richard online, and a few others as well, but I found this a useful intro to the language from the creator, and it was helpful to explain some of the `Task` and result stuff, as well as demoing some core features that are useful to know exist.
* [Roc official examples](https://www.roc-lang.org/examples) List of example programs, and useful to demo what can be done (but certainly not exhaustive)
* [Roc official Docs](https://www.roc-lang.org/docs) self explanatory, but useful docs. Mostly useful docs, it seems like some samples etc. are perhaps out of date? that said this is the source, so good to read it, and have it open while you're exploring.

Next, we'll write a simple hello world program, and play with STDIN/STDOUT and typing based on the 'intro to the roc language' video.
