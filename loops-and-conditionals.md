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

A verbose conditional block like `(if A then B else if C then D else E)` can be rewritten instead as:

`(COND (A B)(C D)(T E))`

{% hint style="info" %}
T marks the default value. If all previous condition checks return NIL, then the argument following T is evaluated.
{% endhint %}

The arguments after COND are referred to as clauses. Each clause is evaluated in order and is a list of the form (P<sub>1</sub> C<sub>1</sub> ... C<sub>1N</sub>). Here, P is the condition to be checked. If P returns true, then C1 to C1N are evaluated sequentially.











