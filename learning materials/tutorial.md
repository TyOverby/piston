# Piston Tutorial

*Notice! Piston is currently undergoing drastically changes and this tutorial might be outdated.*

## Introduction

Piston is a game engine focusing on user friendliness, back-end agnostic interface and game development research using the Rust language. With Piston you should be able get something up on the screen quickly, make a prototype, load images and sounds, polish it to look like a real game and port it to other platforms. Our goal is to provide the tools for creative game development, build the best 2D graphics API for Rust and make it easy to use with other libraries for game development in the Rust community. 3D can be achieved through OpenGL.

Rust is a programming language with a focus on type safety, memory safety, concurrency and performance. It is intended for writing large-scale, high-performance software that is free from several classes of common errors. Rust has a sophisticated memory model that encourages efficient data structures and safe concurrency patterns, forbidding invalid memory accesses that would otherwise cause segmentation faults. It is statically typed and compiled ahead of time. For more information see http://www.rust-lang.org/

Some of the things that make Rust suitable for game development:

* Garbage collection is optional which makes it easier to reason about performance
* The Rust enum type is suitable for state machines which are commonly used in game logic
* Exhaustive match helps you cover all states
* Allows low level programming and reuse of existing C libraries
* Link libraries statically to create standalone executables
* Generics & traits makes it possible to build zero cost abstractions
* No null pointer exceptions
* Functional iterator patterns that are optimized at compile time
* Immutability by default which makes it easier to read Rust code
* Flexible module system for organizing large projects
* Active and friendly community with a rapidly growing open source ecosystem

## How to get help

If you experience problems with this tutorial, ask in the [#rust-gamedev](http://chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-gamedev) IRC channel or open an issue in the [Piston](https://github.com/PistonDevelopers/piston/) repository.

## Getting started

### Linux or Mac OSX (with developer tools)

First you have to set up a new Rust project for executable:

1. Create a new folder for your game project
2. Copy 'Makefile' from https://github.com/bvssvni/rust-empty
3. If `rustc --version` gives an error, type `make nightly-install` to install Rust nightly
4. In the Terminal window, type `make exe` and `make git-ignore`

You are now ready for writing Rust programs!  
Before you can start coding, you need to build Piston:  

2. Clone https://github.com/PistonDevelopers/piston-workspace and follow the instructions to build Piston
4. Copy symlinks from the 'piston-symlinks' folder in piston-workspace to your project's 'target/cpu-vendor-os/lib' folder

If you don't have the 'target' folder, use the command `make target-dir`.

You are now ready for making a game in Rust!

## Piston documentation

Online version of the documentation: http://pistondevelopers.github.io/docs/piston/piston/

There are links to online version of the dependencies documentation in [README](https://github.com/PistonDevelopers/piston/blob/master/README.md)

### How to generate documentation

The README.md in https://github.com/PistonDevelopers/piston-workspace tells you how to generate documentation.  
Follow these instructions to generate the documentation for all the projects in one go.  

## How to build the examples

1. Open the Terminal and navigate to the 'piston' project.
2. Type `make examples`

If you use tab out of habit, you will get `make examples/` which will not work.

## Rendering with OpenGL

OpenGL is supported through [hgl-rs](https://github.com/cmr/hgl-rs/) which also comes with Piston-Workspace.

When switching to a custom shader, use `args.gl.use_program(program)`.  
This makes the 2D back-end aware that the current shader has changed.  
