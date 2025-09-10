# Build Your First Interactive Program

Building quick and easy interfaces is one of Medley Interlisp's most powerful features. You can always refer to the Interlisp Reference Manual for an exhaustive list of its GUI capabilities. In the primer, however, we'll learn by building modular interfaces for tools that can be connected to form a larger, coherent system. We'll start with basic forms and upgrade our tools and underlying structures as our understanding of the system grows. For now, it's time to build our first interactive program—a distress call module for a spaceship.&#x20;

In this chapter, we'll learn to do the following things in Medley:

* Build windows.
* Assign variable names to values.
* Build menus and buttons.
* Attach windows and menus.
* Build functions.
* Display function outputs in windows.
* Connect functions to button clicks.

***

Medley has predefined formats to follow when you want to create objects like windows and menus.&#x20;

To create a window, we follow the format: `(CREATEW REGION TITLE BORDERSIZE)`. In the Interlisp Exec, type: `(CREATEW NIL "DISPLAY MODULE" 10)`. You can now click and drag to create a new window with the title DISPLAY MODULE and a border size of 10.&#x20;

`REGION` lets us define the position at which the window will appear and its size. When `NIL`, we can define the region dynamically (by clicking and dragging) like we just did.&#x20;

Predefined regions are useful when we want to create multiple windows of the same type and size. To create a region, we follow the format: `(CREATEREGION LEFT BOTTOM W H)` . LEFT and BOTTOM refer to the pixel distance of the region we're defining from the left and bottom edge of the screen. W and H are the width and height of the window. In the Exec, type:&#x20;

`(CREATEW (CREATEREGION 500 500 300 200) "DISPLAY MODULE" 10)`&#x20;

Do you see your window? Play around with the values to get a feel of the pixel density!&#x20;

Try to create a window with no title and border. Can you make one that looks like a button?

{% hint style="info" %}
Regardless of the region set, we can always change the position, shape and size of our existing windows dynamically through its right-click context menu.
{% endhint %}

***

It's quite easy to create different objects in Medley. But ideally, we want a way a to give them short names so we can call them when we want instead of typing out the entire format every time.&#x20;

`(SETQ NAME VALUE)` will let us assign values to variable names. `VALUE` can be a function, a call to create a window, or any snippet of code for which you need a new name. Let's assign a name to our region first. We can use this name to set the region for our window. We'll also give our window a name.

In the Exec, type: &#x20;

1. `(SETQ window-region (CREATEREGION 500 500 300 200))`

Medley is now aware of a new region named `window-region`. We can use this region for any new window we make.

2. `(SETQ display-window (CREATEW window-region "DISPLAY MODULE" 10))`&#x20;

This creates a new variable `display-window` which when called will create a new window at the region `window-region`.

3. We can open or close this window with `(OPENW display-window)` and `(CLOSEW display-window)`.

{% hint style="info" %}
We don't write variable names inside " " because they are not static strings to store but data containers that Medley can open.
{% endhint %}

***

Menus are windows that can have menu-like items and subitems. A cool way to refactor menus is to create a menu with no title and one item which appears and acts like a button.

Menu creations follow the format:&#x20;

`(CREATE MENU TITLE ← "NAME" ITEMS ← '(ITEM1 ITEM2 ITEM3))`

{% hint style="info" %}
You can insert the left arrow in Medley by typing the underscore symbol. If you need a combination of keys for underscore, they should produce a left arrow in Medley.
{% endhint %}

Creating a menu defines a menu object in the background but doesn't create an instance of it on our screen. To do that we can use: `(MENU NEWMENU POSITION)` where the first `MENU` tells Medley to create a new menu with the name `MENU` at `POSITION` . Example: `(MENU button-menu 700 200)` . This is just an example and won't work because button-menu hasn't been defined yet.

Similar to MENU, we can also use:

* `(ATTACHMENU button-menu display 'TOP 'CENTER)` : Attaches the menu `button-menu` to the window `display` at the top, centered.
* `(ADDMENU button-menu display)` : Adds `button-menu` to the bottom-left corner of `display-window` .&#x20;

In your Exec type:

1. `(SETQ button-menu (CREATE MENU ITEMS ← '("NAVIGATION SYSTEM FAILURE")))`&#x20;

This creates a menu called `button-menu` with no title and one item only.

2. `(ATTACHMENU button-menu display-window 'LEFT 'CENTER)`\
   You should see a button-like window appear on the left edge of the window `display-window`with the text "NAVIGATION SYSTEM FAILED".
3. Right now, the button doesn't do anything. Next, we'll connect a function to the button which can print text to `display-window` .

{% hint style="info" %}
We can detach and remove this menu with  `(DELETEMENU button-menu display-window)` . This does not delete the menu from memory. You can always repeat Step 2 to reattach the menu.
{% endhint %}

***

Let's create a list of distress calls we can randomly cycle through each time we press our button! In your Exec, type:

{% code overflow="wrap" lineNumbers="true" fullWidth="false" %}
```lisp
(SETQ distress-calls (LIST
"Help! Nav systems compromised. What is lost will never be found."
"Help! Nav systems compromised. Lethal solar flare imminent."
"Help! Nav systems compromised. Stuck in orbit. Planetfall- ETA: 2 cycles."
"Help! Nav systems compromised. Class 3 Destroyer approaching. Contact- ETA: 6 cycles."
"Help! Nav systems compromised. Direction constant but unknown. Debris field. Contact- High."
))
```
{% endcode %}

Now, that we have a list named `distress-calls` , we can set up a function called `nav-sys` that displays a random message from this list to our `display-window` . Next, we'll connect this function to our `button-menu`.

***

We can define a new function with `DEFINEQ` . In your Exec, type:

{% code title="" overflow="wrap" lineNumbers="true" %}
```lisp
(DEFINEQ (nav-sys (LAMBDA (X) 
(PRIN1 (CAR (NTH distress-calls (RAND 1 (LENGTH distress-calls)))) 
display-window))))
```
{% endcode %}

Let's break down our function:

1. `nav-sys`: Name of function
2. `PRIN1`: for printing to a specific window
3. `CAR`: returns the first element of a list
4. `(NTH list number)`: returns the tail of the specified `list`starting from the specified `number`. So, if we have a list `(A B C D)` and we use `(NTH (ABCD) 2)`, we'll get `(B C D)` as the output.
5. `(RAND value1 value2)`: returns a random value in a range from `value1` from `value2`.
6. `(LENGTH list)`: returns the length of the list.
7. `(CAR (NTH distress-calls (RAND 1 (LENGTH distress-calls))))` :&#x20;
   1. `(RAND 1 (LENGTH distress-calls))` returns a random number between 1 and the total length of the list `distress-calls`.
   2. `(NTH distress-calls` returns the tail of the list starting from the element at that random number.
   3. `(CAR` returns the first element of that tail.
   4. `(PRIN1 ... display-window)` prints that element to `display-window` .
   5. And of course, `(DEFINEQ (nav-sys (LAMBDA (X)` gives the name `nav-sys` to our function. For our current function, we have no use for any parameters, so X is declared following conventions but unused.

***

Let's delete the button we made before with `(DELETEMENU button-menu display-window)` .

We'll make a new `nav-button` with our `nav-sys` function attached!

In your Exec, type:

{% code overflow="wrap" lineNumbers="true" %}
```lisp
(SETQ nav-button 
(CREATE MENU 
ITEMS ← '("NAVIGATION SYSTEM FAILURE")
WHENSELECTEDFN ← (FUNCTION nav-sys)
))
```
{% endcode %}

Our new button only has a small addition (and a different name).&#x20;

`WHENSELECTEDFN ← (FUNCTION nav-sys)` executes the function `nav-sys` when menu-item (our button `nav-button` ) is selected.

Go ahead and interact with your button!

Is your distress call module working? Cool! In the upcoming chapters, we'll add more features to our Display Module. While building this project, for each feature we'll explore and learn new bits of Medley Interlisp!







