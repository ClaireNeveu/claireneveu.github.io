---
layout: post
title:  "Type Systems for Beginners"
date:   2024-04-10 12:02:58 -0400
categories: programming types fundamaental
---
As more advanced type systems become commonplace thanks to projects like Typescript I've seen otherwise quite capable programmers shrink away from types. More than one person has expressed to me that they are not capable of working on anything but the simplest of types. I think this is more a marketing problem than an issue of technology. Type systems are unique among technologies that you will work with as a programmer in that they are designed expressly to be understandable to you before any other concern.

In this series I want to help you build up an intuition about type systems, what they're for, and how to use them to improve your programming. You don't need to understand any particular programming language to read this series. I will occasionally reference programming languages which contain the concepts I'm discussing but all code examples will be in an imaginary language we'll call Toy.

Let's get started.

# Types

The most fundamental idea in programming is also the most fundamental idea in type systems. Here's a function in Toy that adds numbers together:

```
>>> add(1, 2)
3
```

In this example `>>>` denotes an expression in Toy and the following line shows what it evaluates to. I'll be using a standard syntax[1] for toy that should be familiar to you. How would you describe this function? "add is a function that performs mathematical addition on its arguments" sounds pretty good. Let's test it out:

```
>>> add(1, 2, 3)
ERROR("add() expected 2 arguments but 3 were given")
```

It looks like our definition was not precise enough, let's refine it: "add is a function. If it receives two arguments it performs mathematical addition on them otherwise it returns an error". What if we pass it strings instead of numbers:

```
>>> add("foo", "bar")
ERROR("add() expected integer but string was given")
```

We'll make one final adjustment to our definition: "add is a function. If it receives two integer arguments it performs mathematical addition on them otherwise it returns an error". This definition of what the function is and how we use it is the function's **type**. We might also call it the function's **true type** since it is not constrained by the limitations of a particular type system.

Toy does not do any type-checking, it is an untyped or dynamically-typed language but Toy's `add` function *still has a type*. This is the first thing to understand about type systems: when we talk about **types** we are just talking about what a thing is or does.

# Type Annotations

English sentences are not a great way to describe types; they are long, unstandardized, and inaccessible to non-English speakers. They are also not machine readable which is important if we want a computer to help us with our typing. We can introduce a standard type language for our Toy examples but we will have to make _choices_, there is no one correct way to do it. I'll give you a few ways and then we'll pick one to build on.

In all of these examples `a : b` will mean that `a` has type `b` and `(n) -> r` will mean a function that take a value of type `n` and returns a value of type `r`.

```
add : <a>(a, a) -> a is integer ? integer : error
```
This first example introduces a way of denoting "generic types". `<a>` before a function type introduces a *wildcard* type which could be anything which is then used for the arguments of `add`. The return type of `add` is a conditional type which results in `integer` if `a is integer` otherwise `error`.

This definition is a little hard to read since it moves most of the important information into the return type.

```
add : (integer, integer) -> integer
add : (not<integer>, not<integer>) -> error
```
This example introduces "overloaded types". Instead of one definition we say that `add` has two definitions, one if the arguments are integers and one if the arguments are not integers.


```
add : (integer, integer) -> integer
```
This example is the same as the previous one but we've eliminated the non-integer case. This makes our type definition of integer technically less complete. The important realization in this definition is that the error case for `add` is not *useful*. 


[1] Not everybody has the same experience so here's a breakdown for you. `add` is an *identifier* which points to our function. `1` and `2` are *primitives*, values provided to us by the language. The parentheses and comma mean *function application*. Overall this means: apply the function called "add" to the primitive arguments `1` and `2`.





# Using a Type Checker

## Contracts

## Refactoring

## Inspection