---
description: >-
  The goal of this chapter is to help readers understand how to read Lisp code
  by introducing its key syntax elements and delimiters such as () and '
---

# Understanding Lisp Syntax

#### **Endless Parentheses**

At the heart of Lisp, short for List Processing, are, you guessed it, LISTS! Specifically, lists that start with a left parentheses and close with a right parentheses.&#x20;

`(1 2 3)`

If you are coming from other languages, you might be used to commas as separators for list items. Items in Lisp lists are instead separated by a space.&#x20;

{% hint style="info" %}
This is why when we name things in Lisp, we use separators other than space.

(eg. `function-name` instead of `function name`)
{% endhint %}

A list in Lisp can contain different types of elements from strings, numbers, variables, functions and other lists.&#x20;

`(1 "Medley" (3 5 "Interlisp"))`

The above example is a list with three elements: the number 1, the string Medley and the list (3 5 "Interlisp").

Lists are a powerful data structure for representing homogenous and hierarchical data. While other programming languages have several levels of abstraction to "assist" you in building data structures in various ways, it also results in you having to type a lot of syntactic scaffolding to get to what you need.&#x20;

Lisp, however, is fast and simple. Everything we do in Lisp is a tree of lists or lists within lists within lists...`(you (get (the idea)))`. It's easy for us to read, understand and write and it's easier for the computer to parse what we write into a structure of meaningful interdependent logic.

#### **REPL**

The REPL, short for READ-EVAL-PRINT-LOOP, is a fundamental part of understanding Lisp. Every piece of code you write first goes through the Reader and then the Evaluator. The Reader translates the characters you type into Lisp objects, called symbolic expressions or s-expressions.

On the surface, s-expressions are written with parentheses, such as `(A B C)`, or with dot notation, such as `(A . B)`. Both are just ways of writing lists and pairs so that the Reader can understand them.

Every Lisp list is actually made from pairs. A pair is created by a cons cell, which holds two values: a CAR (the first element) and a CDR (the rest). Lists are a special kind of pair chain where the last CDR is NIL.

For example, the list `(A B C)` is just shorthand for the dotted form `(A . (B . (C . NIL)))`. In other words, the parentheses version is a more convenient way to write a chain of pairs. The dotted form shows the underlying structure explicitly: each cons cell links an element to the rest of the list. We'll talk more about them in the next chapter.&#x20;

The Lisp evaluator processes s-expressions to produce a result. After the reader translates your code into valid s-expressions, the evaluator steps in to interpret them. It determines the correct order of operations, applies functions to arguments, and resolves variable names to their values. The final result is then passed to the printer to be displayed.

The REPL is a mother listener, of sorts. In Lisp, the REPL is always on-ready to read -> evaluate -> print and repeat.

#### **Single Quote ( ' )**

Some s-expressions are self-evaluating, meaning they represent their own value directly. Numbers and strings are great examples; when you type `42` or `"hello"` into the Lisp REPL, the evaluator simply returns that exact value.

However, most other s-expressions are not self-evaluating. The Lisp evaluator tries to interpret them as code, typically a function call. To prevent this from happening and tell Lisp to treat the expression as literal data, you use the special form `quote`.

The single quote symbol (`'`) is a reader macro, a convenience that's processed _before_ evaluation. It's a shorthand that the Lisp reader automatically translates into the `quote` special form. For example, `'expr` is simply a more convenient way of writing `(quote expr)`.

The special form `quote` is handled directly by the evaluator. Unlike a regular function that evaluates its arguments, `quote` prevents its single argument from being evaluated and returns it as is. This is crucial for treating code as data. Let's look at the difference with an example:

* `'(+ 1 2)`: The single quote stops the evaluator from processing `+` as a function. Instead, it treats the expression `(+ 1 2)` as a list of symbols and numbers, returning it as-is. The reader macro `'` expanded this into `(quote (+ 1 2))` for the evaluator.
* `(+ 1 2)`: Without the quote, the evaluator processes `+` as a function and `1` and `2` as its arguments, and returns the result, `3`.

This ability to treat code as data is one of the most powerful and fundamental features of Lisp. It allows you to write programs that can dynamically generate and manipulate other code.

\
