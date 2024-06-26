# Your first CLI program

For this first program, we'll write a CLI program. This brings us the first core concept of the language you'll need to understand, the `platform`.

The platform represents the lifecycle and side effecting layer of your program. This means that for a CLI app, the lifecycle is the invocation and completion of the program, as well as side effecting via things like STDIN/OUT/ERR, access to the file system, networking, and shelling out to other programs. 

These are wrapped in the `basic-cli` platform, though as stated by the language authors, you could conceivaby have a different implementation of a `secure-cli` platform for example, which disallows any network access without explicit user input, but implement the same platform interface.

For info about the basic-cli exposed functionality, refer to the [docs](https://www.roc-lang.org/packages/basic-cli/0.10.0).

## Get to runnable

Initially, we'll just set up our program file in a new directory (location doesn't matter yet), and we'll create a file named `hello.roc`.

The minimal file required to get things working is as follows.

```roc
app [main] {
    cli: platform "https://github.com/roc-lang/basic-cli/releases/download/0.10.0/vNe6s9hWzoTZtFmNkvEICPErI9ptji_ySjicO6CkucY.tar.br",
}

import cli.Stdout

main =
    Stdout.line! "Hello, world!"
```

The first line declares our app, and that we'll be exposing a `main` function. Within the closure of the app we have our imports. There's a single import in this program, `cli` which is a `platform` import that points to a specific release on github. As of June 2024 this is the idiomatic way to take a dependency on a platform or external library. Note that the string is both a a link to the download location, and also includes a signature which is verified against the downloaded dependency.

The second line then imports `Stdout` from the cli platform, meaning we can invoke methods on the Stdout object in our code.

Finally, we declare a `main` method, which is assigned to the function `Stdout.line! "Hello, world!"`

This means that when the code is built and executed, the platform will invoke our `main` function, printing Hello, World! to STDOUT.

This is fine and dandy, but why is there a bang (!) character in the line method?

Line is a side-effecting method, and all side-effecting methods in the Roc stdlib and core platforms will use the bang to indicate this. As of now, it appears you can't create your own methods with the bang in the name.

Let's run our code! You can run this program directly by invoking

```sh
roc dev hello.roc
```

Which will compile your program, and execute it.

You should see `Hello, World!` printed to your STDOUT, and if you look in the directory where you placed `hello.roc` you'll see an executable called `hello` (or `hello.exe` on windows).

If you wish to simply build your program to distribute, you can run `roc build hello.roc` which will create the `hello` executable, not run it.

Congratulations! You've written and run your first Roc program.

Next up, we'll break this program into a few functions, add some interactivity, and add tests via the `expect` keyword.
