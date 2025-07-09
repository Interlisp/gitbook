# Loops and Conditionals

Medley offers a set of useful special forms for conditional and looping logic (eg, AND, OR, FOR, WHILE). It also provides us with a list of functions to compare and understand our data.

You can refer to the [IRM](https://interlisp.org/documentation/IRM.pdf)'s Chapter 9, "Lists and Iterative Statements," for an exhaustive list of available options.

`(FLOATP X)`: Returns x if x is a floating point number. Otherwise returns NIL.

`(NUMBERP X)`: Returns x if x is a number of any type. Otherwise returns NIL.

`(STRINGP X)`: Returns x if x is a string. Otherwise returns NIL.

`(EQP X Y)`: Returns T if x and y are number and equal in value. Otherwise returns NIL.

`(EQUAL X Y)`: Returns T if X and Y are numbers with equal value or strings with the same sequence of characters or lists where CAR of X and Y and CDR of X and Y are equal. Otherwise returns NIL.

#### Conditionals

You may have used if/else statements in other programming languages. `COND` can be used to chain together multiple if/else logic concisely. You can consider it similar to `match` blocks.













