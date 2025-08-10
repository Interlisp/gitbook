# Debugging

Part of what sets Medley apart is a collection of functions and features to help us debug our programs.   Consider `FIX line-number` and `(ED 'function-name)`.

`FIX` lets us edit whatever we typed at a certain line number. It's useful when we want to make an immediate change.

<figure><img src=".gitbook/assets/FIX-GRAVITY.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Remember, we can refer to line numbers from any Exec. You might find it helpful to work with multiple smaller Execs, each focusing on a unique function of the larger program.
{% endhint %}

Back In the SEdit chapter, we learned about editing the definition of a function with `(DF function-name)`, which Medley actually translates to `(ED 'NAME '(FUNCTIONS FNS :DONTWAIT))`.&#x20;

While `DF` is for editing functions only, `ED` is the default editor function we can use to edit any File Manager object, including function definitions, variable values, property lists, or file package commands through SEdit.

{% hint style="info" %}
The :DONTWAIT statement in DF's mapping to ED enables function edits to be tested in the Exec without needing to compile first. Try both DF and ED to edit a function. Does one of them let you switch to the Exec freely? Which one restricts you to SEdit?
{% endhint %}



"If you are setting a variable that is significant to a program and you want to save it on a file, you should use the Common Lisp macro CL:DEFPARAMETER instead of SETQ. This will give the symbol a definition of type VARIABLES (instead of VARS), and it will be noticed by the File Manager. Subseqent&#x20;changes to the variable must be done by another call to CL:DEFPARAMETER or by editing it using ED (not DV)."
