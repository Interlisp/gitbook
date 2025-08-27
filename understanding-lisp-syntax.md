---
description: >-
  The goal of this chapter is to help readers understand how to read Lisp code
  by introducing its key syntax elements and delimiters such as () and '
---

# Understanding LISP Syntax

**Endless Parentheses**

At the heart of LISP, short for List Processing, are, you guessed it, LISTS! Specifically, lists that start with a left parentheses and close with a right parentheses.&#x20;

`(1 2 3)`

If you are coming from other languages, you might be used to commas as separators for list items. Items in LISP lists are instead separated by a space.&#x20;

{% hint style="info" %}
This is why when we name things in LISP, we use separators other than space.

(eg. `function-name` instead of `function name`)
{% endhint %}

A list in LISP  can contain different types of elements from strings, numbers, variables, functions and other lists.&#x20;

`(1 "Medley" (3 5 "Interlisp"))`

The above example is a list with three elements: 1, Medley and (3 5 "Interlisp"). The third element is a nested list. Get ready to see a lot of them throughout this Primer!

Lists are a powerful data structure for representing homogenous and hierarchical data. While other programming languages have several levels of abstraction to "assist" you in building data structures in various ways, it also results in you having to type a lot of syntactic scaffolding to get to what you need.&#x20;

LISP, however, is fast and simple. Everything we do in LISP is a tree of lists or lists within lists within lists...`(you (get (the idea)))`. It's easy for us to read, understand and write and it's easier for the computer to parse what we write into a tree of meaningful interdependent logic.

**REPL**

The REPL, short for READ-EVAL-PRINT-LOOP, is a fundamental part of understanding LISP. Every piece of code you write first goes through the Reader and then the Evaluator. The Reader translates the characters you type into LISP objects, called symbolic expressions or s-expressions.

On the surface, s-expressions are written with parentheses, such as `(A B C)`, or with dot notation, such as `(A . B)`. Both are just ways of writing lists and pairs so that the Reader can understand them.

Every LISP list is actually made from pairs. A pair is created by a cons cell, which holds two values: a CAR (the first element) and a CDR (the rest). Lists are a special kind of pair chain where the last CDR is NIL.

For example, the list `(A B C)` is just shorthand for the dotted form `(A . (B . (C . NIL)))`. In other words, the parentheses version is a more convenient way to write a chain of pairs. The dotted form shows the underlying structure explicitly: each cons cell links an element to the rest of the list. We'll talk more about them in the next chapter.&#x20;

The LISP evaluator processes s-expressions to produce a result. After the reader translates your code into valid s-expressions, the evaluator steps in to interpret them. It determines the correct order of operations, applies functions to arguments, and resolves variable names to their values. The final result is then passed to the printer to be displayed.

The REPL is a mother listener, of sorts. In LISP, the REPL is always on-ready to read -> evaluate -> print and repeat.

**Comments**

We can add a comment in LISP, using a semicolon. In a later chapter, we'll learn to use the powerful structure editor or SEdit in Medley, where we can add comments as documentation for our LISP objects.&#x20;

Three levels of comments are supported in Medley. According to the Interlisp Reference Manual:

> Single-semicolon comments are formatted at the comment column, about three-quarters of the way across the window. Doublesemicolon comments are formatted at the current indentation of the code they are in. Triple semicolon comments are formatted against the left margin. The level of a comment can be increased or decreased by pointing after the semicolon, and either typing another semicolon, or backspacing over the preceding semicolon.

**Single Quote**

Some s-expressions are self-evaluating. Such as numbers and strings (delimited by " "). Meaning, we don't need to explicitly tell LISP to process them as data. All other elements in our lists, however, need an explicit flag to communicate to LISP "read what comes right after as raw data and don't evaluate it)".

`quote` or `'` tells LISP not to evaluate what follows.

Try: `'(+ 1 2)`  and `(+ 1 2)`  in the Exec window.

`'(+ 1 2)` prints `(+ 1 2)`. LISP did not evaluate the expression and printed an exact copy.

`(+ 1 2)` prints `3`. LISP evaluates this expression as intended.

This is a powerful feature of LISP, we'll explore later. `quote` gives us the ability to treat our functions as data!



\
