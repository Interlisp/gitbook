# Debugging

Part of what sets Medley apart is a collection of dedicated functions and features to help us debug our programs.

#### **FIX and ED**

`FIX line-number` :

`FIX` lets us edit whatever we typed at a certain line number. It's useful when we want to make an immediate change.

<figure><img src=".gitbook/assets/FIX-GRAVITY.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Remember, we can refer to line numbers from any Exec. You might find it helpful to work with multiple smaller Execs, each focusing on a unique function of the larger program.
{% endhint %}

Back In the SEdit chapter, we learned about editing the definition of a function with `(DF function-name)`, which Medley internally translates to `(ED 'NAME '(FUNCTIONS FNS :DONTWAIT))`.&#x20;

&#x20;`(ED 'function-name)`:

While `DF` is for editing functions only, `ED` is the default editor function we can use to edit any File Manager object, including function definitions, variable values, property lists, or file package commands through SEdit.

{% hint style="info" %}
The :DONTWAIT statement in DF's mapping to ED enables function edits to be tested in the Exec without needing to compile first. Try both DF and ED to edit a function. Does one of them let you switch to the Exec freely? Which one restricts you to SEdit?
{% endhint %}



***

#### **INSPECT**

At times, you will define variables that are larger, more complex than an atom. As our programs grow larger, we might want to take a quick look at the contents of these variables in an organized, tabular format without opening an editor like SEdit:

<figure><img src=".gitbook/assets/ed sedit.png" alt=""><figcaption></figcaption></figure>

`INSPECT`allows us to do exactly that:

<figure><img src=".gitbook/assets/inspect menu.png" alt=""><figcaption></figcaption></figure>

Select **Inspect** from menu and a window appears with two columns. The first column displays the numbered positions of the list items and the second column displays the item in that position.

<figure><img src=".gitbook/assets/inspecting x.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Notice how we use quote (') before the variable name when we need to edit the definition of the variable. The system does not need to evaluate or understand the contents. It only needs to display itself for us to make changes. Quote (') tells Lisp not to evaluate or "run" what follows.\
\
But when it comes to Inspect, we do want the system to understand the contents of the list so it can organize and display it neatly for us to review. No quotes for that operation!
{% endhint %}
