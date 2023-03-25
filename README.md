# nice-lang
A scripting language designed to be useful.

> The name is a place-holder.

## Licensing

The entire toolchain, meaning all source code of all the interpreters and other tools in this repository, is under GPL3 license. 

The language specification, meaning the markdown files, is under MIT license.

## Overview

Nice Lang (NL) has the goal of being *useful*:
- It's not trying to be the easiest language, although it is easy enough to be useful. 
- It's not trying to be the most performant language, although it is performant enough to be useful.
- It's not the most concise language, although it is concise enough to be useful.
- It's fairly minimal, as it doesn't include things that aren't very useful, and as a consequence it's also not very difficult to learn.

It's inspired by Python, Ruby and ML languages like OCaml. 

Python is, in my opinion, the most useful language. It is extremely productive, quite easy to learn, has good package management and a great standard library. It's performance is not great, but it's okay for many applications. It has a dynamic type system, but it has some support for static type checking. Also its type system, while dynamic, doesn't constantly try to back-stab you like JavaScript does.

Python, however, is getting old, and some of its design choices are a bit questionable. It's a bit too late to change them now, so as Python developers, we have to learn to work around them. NL aims to provide a coding experience similar to Python, but hopefully improve on some of its weird design decisions.

In particular, NL's largest departure from Python in its type system, which is heavily inspired by ML languages, and borrows some tricks from Julia in the way function dispatching is handled.

If you are familiar with a more traditional and imperative Python style, the language might not resemble Python that much, that's because NL is based on a modern and declarative Python style. With dataclasses, type hints and pattern matching.

Some other differences are:
- Structs instead of objects. Inheritance is completely removed as a mechanism, instead you can use sum types or composition.
- Methods are just normal functions that operate on their first argument, with some syntax sugar to make them more method-like. The combination of structs and methods feels a lot like working with Python dataclasses.
- True multi-threading support
- No significant whitespace (except for newlines). Instead, blocks are terminated with the `end` keyword.
- Enforced variable privacy
- Variables are immutable by default, and mutability is enabled explicitly
- Support for const variables, where they must be evaluated at definition-time, not at run-time, or they will raise an error
- Rust-like error handling
- Pass-by-value by default, instead of the confusing pass-by-object semantics of Python.

Some of the features of Python that I love the most, are also here:
- List, set and dictionary comprehension
- Superpowered slicing
- Native UTF-8 strings

See: [Comparison with Python](comparison-python.md)
