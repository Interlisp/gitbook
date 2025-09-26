# Atoms, Functions and Lists

#### Atoms and S-Expressions

The smallest parts of Lisp code are called atoms. An atom can be a number, a symbol, or a name that identifies a function or variable. Some atoms are built into the language, like `+` for addition, while others are defined by the programmer, like variable names or custom function names.

Everything in Lisp, whether an atom or a collection of atoms, is represented as a symbolic expression, or s-expression. Atoms are s-expressions by themselves, while lists are s-expressions that contain other s-expressions, written with parentheses: `(A B C)` is a list containing three s-expressions.

By combining atoms into lists and other s-expressions, we can build more complex logic and programs.

#### Functions

Functions are reusable tasks broken down into steps for computers to understand. A function is made of three key components:

(1) A name so we can call it. Calling a function tells the computer to start the task.&#x20;

In Interlisp, we can define a function with `DEFINEQ` .&#x20;

`(DEFINEQ (function-name (LAMBDA (X Y) (PRINT X) (PRINT Y))))` defines a function called function-name with the arguments `X` and `Y` and the "forms" `(PRINT X)` and `(PRINT Y)`.&#x20;

We call functions by enclosing them in parentheses: `(function-name X Y)`.

{% hint style="info" %}
Make sure you are in an Interlisp Exec. DEFINEQ is specific to Interlisp and won't work for Common Lisp.
{% endhint %}

(2) A set of directions telling the computer how to perform the task.&#x20;

`LAMBDA` tells Interlisp to evaluate the arguments when the function is called before moving on to executing the forms that follow. We can also use `NLAMBDA`, which does not evaluate arguments before executing forms.

To clarify:&#x20;

LAMBDA: `(DEFINEQ (adder (LAMBDA (X  Y) (+ X Y))))`

* When called `(adder 3 (+ 3 4))` outputs `10`because the LAMBDA function evaluated `(+ 3 4)` before assigning that value to `Y` . So, the output is X (3) + Y (7) = 10.

NLAMBDA: `(DEFINEQ (n-adder (NLAMBDA (X Y)(+ X Y))))`

* When called `(n-adder 3 (+ 3 4))` outputs `(+ 3 4) is not a NUMBER` because it expects `Y` to be  a number that `+`can add to `X` (3) but instead encounters an expression which it has been told not to evaluate by NLAMBDA.

(3) Forms that lay out the logic the function should execute. Think of forms as logic encapsulated as lists that uses the arguments passed.

`(DEFINEQ (seven (LAMBDA NIL (+ 3 4))))`  outputs `7`. The expression `(+ 3 4)` is the last form in the function body.

You probably already know what functions are if you're coming from another programming language. Functions help us organize our code and save us the trouble of repeating ourselves. Think of them as an easy way to ask the computer to complete a complex task. Rather than describing the task every time, we describe it once and call it by its name when needed. A good practice is to make function names simple but descriptive.&#x20;

{% hint style="info" %}
Refer to the [Interlisp Reference Manual's](https://interlisp.org/documentation/IRM.pdf) FUNCTION DEFINITION, MANIPULATION AND EVALUATION chapter to learn more about functions!
{% endhint %}

#### Lists

A list in Lisp is an ordered collection of s-expressions enclosed in parentheses. Lists are fundamental to Lisp because the name itself stands for List Processing. A list can contain atoms, such as numbers or symbols, and other s-expressions. Lists allow Lisp to represent sequences of operations, arguments for functions, or structured data. By combining atoms and lists in this way, we can build expressions of any complexity.

One of Lisp's special powers is _homoiconicity-_ the ability to represent both code and data using the same structure: lists. Most programming languages let us automate the manipulation of data. In Lisp, we can go further: we can manipulate our logic/code as data. This opens the door to inspecting, transforming, or even generating code programmatically. Pretty cool!

`CONS` is the primary function for constructing pairs in Lisp. Each pair, called a **cons cell**, contains exactly two parts:

* The **CAR**, which holds the first element
* The **CDR**, which holds the second element

These are historical terms that have persisted from the early days of Lisp. To make them easier to read, Common Lisp also defines `FIRST` as an alias for `CAR` and `REST` as an alias for `CDR`.

Every list in Lisp is made from cons cells linked together. A single cons cell can hold atoms or other cons cells in either its CAR or CDR. Lists end when a CDR is `NIL`.

For example:

* `(CONS 1 2)` produces the dotted pair `(1 . 2)`. Here `1` is the CAR and `2` is the CDR.
* `(LIST 1 2 3)` produces `(1 2 3)`, which is shorthand for `(CONS 1 (CONS 2 (CONS 3 NIL)))`. Each cons cell links one element to the rest of the list.

In other words, `LIST` is just a convenient way to build a chain of cons cells.

{% hint style="info" %}
To wrap your head around the relationship between atoms, lists, and functions, consider this: We can build functions by combining atoms into a list. Our function can be given a name. This name, a symbol, can be used as an atom alongside other atoms in a new list.
{% endhint %}



