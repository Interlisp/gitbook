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

To create a window, we follow the format: `(CREATEW REGION TITLE BORDERSIZE)`. In the Exec, type: `(CREATEW NIL "DISPLAY MODULE" 10)`. You can now click and drag to create a new window with the title DISPLAY MODULE and a border size of 10.&#x20;

`REGION` lets us define the position at which the window will appear and its size. When `NIL`, we can define the region dynamically (by clicking and dragging) like we just did.&#x20;

Predefined regions are useful when we want to create multiple windows of the same type and size. To create a region, we follow the format: `(CREATEREGION LEFT BOTTOM W H)` . LEFT and BOTTOM refer to the pixel distance from the left and bottom edge of the screen where the window should spawn. W and H are the width and height of the window. In the Exec, type:&#x20;

`(CREATEW (CREATEREGION 500 500 300 200) "DISPLAY MODULE" 10)`&#x20;

Do you see your window? Play around with the values to get a feel of the pixel density! Can you create windows with no titles and no borders? Can you make windows shaped like buttons?

{% hint style="info" %}
Regardless of the region set, we can always change the position, shape and size of our existing windows dynamically through its right-click context menu.
{% endhint %}

***

It's quite easy to create different objects in Medley. But ideally, we want a way a to give them short names so we can call them when we want instead of typing out the entire format every time.&#x20;

`(SETQ NAME VALUE)` will let us assign values to variable names. `VALUE` can be a function, a call to create a window, or any snippet of code for which you need a new name. Let's assign a name to our region first. We can use this name to set the region for our window. We'll also give our window a name.

In the Exec, type: &#x20;

1. `(SETQ window-region (CREATEREGION 500 500 300 200))`

Medley is now aware of a new region named `window-region`. We can use this region for any new window we make.

2. `(SETQ display-window (CREATEW window-region "DISPLAY WINDOW" 10))`&#x20;

This creates a new variable `display-window` which when called will create a new window at the region `window-region`.

3. Create a couple of instances of our new window by typing `display-window` in the Exec.

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
* `(ADDMENU button-menu display)` : Adds `button-menu` to the bottom-left corner of `display` .&#x20;

In your Exec type:

1. `(SETQ button-menu (CREATE MENU ITEMS ← '("NAVIGATION SYSTEM FAILED"))`&#x20;

This creates a menu called `button-menu` with no title and one item only.

2. `(ATTACHMENU button-menu display 'LEFT 'CENTER)`

You should see a button-like window appear on the left edge of the window `display` with the text "NAVIGATION SYSTEM FAILED".

{% hint style="info" %}
Right now, the button doesn't do anything. Next, we'll connect a function to the button which can print text to `display` .
{% endhint %}

***

We can define a new function with `DEFINEQ` . In your Exec, type:

`(DEFINEQ (print2display (LAMBDA (X) (PRIN1 "Help! Navigation system compromised. What is lost will never be found." display))))`

This tells Medley to create a function called print2display which has a parameter `X`and a definition `(PRIN1 "Help! Navigation system compromised. What is lost will never be found." display)` .

The function `prints2display`prints the text in the window `display` .

\[unfinished section about creating lists and cycling through them]









