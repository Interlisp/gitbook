# Understanding and Navigating the Interface

Right after you start Medley, [assuming you've used -a flag to load the full version](#user-content-fn-1)[^1], you should see five four distinct sections making up the interface on your screen.&#x20;

#### The Executive Window

The Executive Window or Exec on the left is the primary window where we can write programs and write code to run other features of Medley Interlisp. There are two flavors of the executive window: Interlisp and Common Lisp. The type you're using is displayed in the title bar of the executive window.&#x20;

You can create more executive windows in your LISP flavor of choice through the EXEC menu item. Keep on reading to learn more about menus. Yes, you can have multiple executive windows present at the same time.

When you start Medley, the default executive window prints some system information (which you can ignore) followed by the flavor. A blinking caret/indicator shaped like the head of an upward pointing arrow on Line 3 tells you the system is ready for input. This is where we'll type (for now!).

<figure><img src=".gitbook/assets/EXEC (INTERLISP).png" alt=""><figcaption></figcaption></figure>

❕When you have multiple executive windows open, each Exec keeps track of which number of window it is (as in: is this the second or third or the seven-hundredth exec) and the line number in relation to the other execs present. So, if you're on Line 8 on one window, the new line when you switch to a new window will be Line 9, even if the previous line was something else.

#### Prompt Window:

The prompt window at the top-left part of the screen (on top of the starting Exec) is a dedicated area for displaying system prompts and messages. We can print our own text here as well.

<figure><img src=".gitbook/assets/Prompt Window.png" alt=""><figcaption></figcaption></figure>

#### Help and Features:

On your right is a section titled Documentation. It's a list of web links to helpful resources to aid you during your time with Medley Interlisp. As a beginner, the PRIMER is a good place to start. BASICS will take you to the Medley Interlisp Project website's Documentation page. Take your time to browse around because chances are the team behind the project has already answered some of the more common questions and curiosities. MANUAL leads to the Interlisp Reference Manual (IRM). Refer to the IRM when you want to know more about certain aspects of Interlisp and when you're ready to move beyond the primer. We'll learn about Notecards and Rooms in later chapters.

<figure><img src=".gitbook/assets/DOCUMENTATION.png" alt=""><figcaption></figcaption></figure>

Menus:

You can open different menus depending on context.\
\
The background menu, which provides general commands, can be accessed by holding down the right mouse button on any empty space on the screen:

<figure><img src=".gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Window-specific menus, which offer options unique to the type of window you’re using. They can be brought up by holding down the middle mouse button on the title bar (but not all windows have a context-specific menu):

<figure><img src=".gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

and the window-management menu, which appears the same for all windows and helps you modify and arrange your windows:

<figure><img src=".gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

Because Medley Interlisp is a 30-year-old system, navigating the interface is slightly different than the modern computers we are used to. But fear not; your mouse and keyboard are all you need!&#x20;

To select a menu item: Press and hold the right mouse button, move the pointer over the item you want, and then release the right button. The highlighted item will be selected.&#x20;

<figure><img src=".gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

To expand a menu item: If the item has a gray arrow, sliding the pointer over it will open a submenu; again, release the right button when the item you want is highlighted. You can technically switch which mouse button is held down while navigating, as long as one button stays pressed, but this is rarely necessary.

<figure><img src=".gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

We can also create our own menus and repurpose them for different tasks. You'll learn more about this moving forward!

[^1]: correct later
