# Atoms, Functions and Lists

#### Atoms

The smallest parts of our code are called atoms. We use them as building blocks for larger tasks. They can be identifiers, symbols, and data. Some atoms are built into the language and help with common tasks, like + for addition. Others are defined by the programmer, like the names of variables or functions.

As we continue, we’ll learn how to combine basic atoms to create more complex logic and programs.&#x20;

Note: Don't confuse atoms with operators and syntax elements, which are structural tools that tell the computer how to read our code. In contrast, atoms are the smallest pieces of code in relation to the task at hand.

#### Functions

Functions are reusable tasks broken down into steps for computers to understand. A function is made of three key components:

(1) A name so we can call it. Calling a function tells the computer to start the task. \[Add: How to define a function in Interlisp]

(2) A set of directions telling the computer how to perform the task. \[Add: What marks the beginning and end of arguments in a function?]

(3) Optional parameters that let us change one or more criteria of a task without having to change the underlying flow of logic. \[Add: Where to add parameters]

Functions help us organize our code and save us the trouble of repeating ourselves. Think of them as an easy way to ask the computer to complete a complex task. Rather than describing the task every time, we describe it once and call it by its name when needed. A good practice is to make function names simple but descriptive.&#x20;

#### Lists

Lists are ordered groups of atoms enclosed in parentheses. They are fundamental to LISP, as you might have guessed, since LISP is an abbreviation for List Processing. They are how we do things rather than what we do. Lists can contain instructions, data, and other lists.&#x20;

One of LISP's special powers is homoiconicity, the ability to treat both code and data as data (inside lists). Programming languages let us automate changing our data. In LISP, we can treat our logic as data and automate its modification as well. Cool!

To wrap your head around the relationship between atoms, lists, and functions, consider this: We can build functions by combining atoms into a list. Our function can be given a name. This name, a symbol, can be used as an atom alongside other atoms in a new list.

