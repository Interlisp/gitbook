# Atoms, Functions and Lists

#### Atoms

The smallest parts of our code are called atoms. We use them as building blocks for larger tasks. They can be identifiers, symbols, and data. Some atoms are built into the language and help with common tasks, like + for addition. Others are defined by the programmer, like the names of variables or functions.

As we continue, we’ll learn how to combine basic atoms to create more complex logic and programs.&#x20;

Note: Don't confuse atoms with operators and syntax elements, which are structural tools that tell the computer how to read our code. In contrast, atoms are the smallest pieces of code in relation to the task at hand. _Understanding LISP Syntax_ can tell you more about LISP's syntactic choices.

#### Functions

Functions are reusable tasks broken down into steps for computers to understand. A function is made of three key components:

(1) A name so we can call it. Calling a function tells the computer to start the task.&#x20;

We can define a function with `DEFINEQ` .&#x20;

`(DEFINEQ (function-name (LAMBDA (X Y) (PRINT X) (PRINT Y))))` defines a function called function-name with the arguments `X` and `Y` and the "forms" `(PRINT X)` and `(PRINT Y)`.&#x20;

We call functions by enclosing them in parentheses: `(function-name)` . There are times when we have to explicitly write `(FUNCTION function-name)`. We'll discuss that in later chapters.

(2) A set of directions telling the computer how to perform the task.&#x20;

`LAMBDA` tells Interlisp to evaluate the arguments when the function is called before moving on to executing the forms that follow. We can also use `NLAMBDA`, which does not evaluate arguments before executing forms.

To clarify:&#x20;

LAMBDA function: `(DEFINEQ (adder (LAMBDA (X  Y) (+ X Y))))`

* When called `(adder 3 (+ 3 4))` outputs `10`because the LAMBDA function evaluated `(+3 4)` before assigning that value to `Y` . So, the output is X (3) + Y (7) = 10.

NLAMBDA function: `(DEFINEQ (n-adder (NLAMBDA (X Y)(+ X Y))))`

* When called `(n-adder 3 (+ 3 4))` outputs `(+ 3 4) is not a NUMBER` because it expects `Y` to be  a number that `+`can add to `X` (3) but instead encounters an expression which it has been told not to evaluate by NLAMBDA.

(3) Forms that lay out the logic the function should execute. Think of forms as logic encapsulated as lists that uses the arguments passed.

We don't necessarily have to include arguments. We could write: `(DEFINEQ (seven (LAMBDA NIL (+ 3 4))))` which just outputs `7`. `(+ 3 4)` is the form of the argument.

Functions help us organize our code and save us the trouble of repeating ourselves. Think of them as an easy way to ask the computer to complete a complex task. Rather than describing the task every time, we describe it once and call it by its name when needed. A good practice is to make function names simple but descriptive.&#x20;

{% hint style="info" %}
Refer to the [Interlisp Reference Manual's](https://interlisp.org/documentation/IRM.pdf) FUNCTION DEFINITION, MANIPULATION AND EVALUATION chapter to learn more about functions!
{% endhint %}

#### Lists

Lists are ordered groups of atoms enclosed in parentheses. They are fundamental to LISP, as you might have guessed, since LISP is an abbreviation for List Processing. They are how we do things rather than what we do. Lists can contain instructions, data, and other lists.&#x20;

One of LISP's special powers is homoiconicity, the ability to treat both code and data as data (inside lists). Programming languages let us automate changing our data. In LISP, we can treat our logic as data and automate its modification as well. Cool!

`CONS` is the primary function for constructing pairs in LISP. Each pair, called a **cons cell**, contains exactly two parts:

* The **CAR**, which holds the first element
* The **CDR**, which holds the second element

These are historical terms that have persisted from the early days of LISP. To make them easier to read, Common Lisp also defines `FIRST` as an alias for `CAR` and `REST` as an alias for `CDR`.

Every list in LISP is made from cons cells linked together. A single cons cell can hold atoms or other cons cells in either its CAR or CDR. Lists end when a CDR is `NIL`.

For example:

* `(CONS 1 2)` produces the dotted pair `(1 . 2)`. Here `1` is the CAR and `2` is the CDR.
* `(LIST 1 2 3)` produces `(1 2 3)`, which is shorthand for `(CONS 1 (CONS 2 (CONS 3 NIL)))`. Each cons cell links one element to the rest of the list.

In other words, `LIST` is just a convenient way to build a chain of cons cells.

{% hint style="info" %}
To wrap your head around the relationship between atoms, lists, and functions, consider this: We can build functions by combining atoms into a list. Our function can be given a name. This name, a symbol, can be used as an atom alongside other atoms in a new list.
{% endhint %}



