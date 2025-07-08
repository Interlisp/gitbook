# Loops and Conditionals

Medley provides a set of useful functions to set up conditional and looping logic. It also gives us a large list of functions to compare and understand our data.

You can always refer to the [IRM](https://interlisp.org/documentation/IRM.pdf)'s Chapter 9 on _Lists and Iterative Statements_ for an exhaustive list of options available.

`(FLOATP X)`: Returns x if x is a floating point number. Otherwise returns NIL.

`(NUMBERP X)`: Returns x if x is a number of any type. Otherwise returns NIL.

`(STRINGP X)`: Returns x if x is a string. Otherwise returns NIL.

`(EQP X Y)`: Returns T if x and y are number and equal in value. Otherwise returns NIL.

`(EQUAL X Y)`: Returns T if:

* X and Y are numbers with equal value
* or strings with the same sequence of characters
* or lists where CAR of X and Y and CDR of X and Y are equal.&#x20;
* Otherwise returns NIL.

..











