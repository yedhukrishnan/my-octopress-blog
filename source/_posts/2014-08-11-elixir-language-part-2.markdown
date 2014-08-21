---
layout: post
title: "Elixir Language (Part 2)"
date: 2014-08-11 22:23:39 +0530
comments: true
categories: [technical, elixir, functional programming] 
---

Here are the few things I liked about the language at the first glance:

### Lists and Tuples

Square brackets are used in Elixir to specify a list of values. They can hold values of multiple data types. 

``` elixir
iex> [1, 2, true, :atom, 3]
[1, 2, true, :atom, 3]
```

They are represented in memory using linked lists. This means accessing the length of a list is a linear operation.

Tuples, unlike lists, store elements contigiuously in memory. They can also hold values of any type.

``` elixir
iex> {:ok, "hello"}
{:ok, "hello"}
```

### Short-Circuit Operators: `and, or`

By default, `and` and `or` operators are short-circuit operators in Elixir. That means, the right hand side of these operators will be executed only if the left hand side is not enough to determine the result.

``` elixir
iex> false and error("This error will never be raised")
false

iex> true and error("This error will never be raised")
** (RuntimeError) undefined function: error/1
```

Here, the first expression returns false because `false and anything` is always false. But in the second part, the left hand side is not enough to get the result. Hence, it tries to execute the right hand side, and it fails because there is no function called `error/1`.

In the next part, I'll share what I learned and liked about the match operator in Elixir.

*Read more:*

* *[(Linked) Lists][basic_types]*
* *[Basic Operators][basic_operators]*
* *[Short-Circuit Evaluation (wikipedia)][short_circuit]*

[basic_types]: http://elixir-lang.org/getting_started/2.html
[basic_operators]: http://elixir-lang.org/getting_started/3.html
[short_circuit]: http://en.wikipedia.org/wiki/Short-circuit_evaluation