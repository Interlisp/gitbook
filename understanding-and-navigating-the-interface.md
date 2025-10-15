# Understanding and Navigating the Interface

After you start Medley, you should see five distinct sections making up the interface on your screen: the prompt window and the executive window on the left, a bar displaying system information at the top, and the Medley Interlisp logo and a Documentation and Optional Features section on the right.&#x20;

<figure><img src=".gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

#### The Executive Window

The Executive Window, or Exec on the left, is the primary window where we can write programs and code to run other features of Medley Interlisp. There are two flavors of the executive window: Interlisp and Common Lisp. The type you're using is displayed in the title bar of the executive window.&#x20;

You can create more executive windows in your LISP flavor of choice through the EXEC menu item. Keep on reading to learn more about menus. Yes, you can have multiple executive windows present at the same time.

When you start Medley, the default executive window prints some system information (which you can ignore), followed by the flavor. A blinking caret/indicator shaped like the head of an upward-pointing arrow on Line 3 tells you the system is ready for input. This is where we'll type (for now!).

<figure><img src=".gitbook/assets/EXEC (INTERLISP).png" alt=""><figcaption></figcaption></figure>

❕When you have multiple executive windows open, each Exec keeps track of which number of window it is (as in: is this the second, third, or the seven-hundredth exec) and the line number in relation to the other execs present. So, if you're on Line 8 on one window, the new line when you switch to a new window will be Line 9, even if the previous line was something else.

#### Prompt Window:

The prompt window, located at the top-left part of the screen (above the starting Exec), is a dedicated area for displaying system prompts and messages. We can print our own text here as well. The prompt window displays useful information about your current task and will ask you for the next step.

<figure><img src=".gitbook/assets/Prompt Window.png" alt=""><figcaption></figcaption></figure>

#### Who-Line:

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

This bar displays a bunch of important system information we can gloss over for now. If you left-click on Rdtbl, you'll see a menu appear with options for how Medley should read our syntax. Interlisp, the default readtable, is case-sensitive (so FUNCTION-NAME and function-name are not the same functions).&#x20;

Sometimes, Medley's error-checking module will interpret the right case even if you make a mistake or ask you for confirmation. But if you want a smoother typing experience without having to worry about case, you could switch to the XCL Rdtbl, which treats upper and lower case letters as the same.

#### Help and Optional Features:

To your right is a section titled 'Documentation'. It's a list of web links to helpful resources to aid you during your time with Medley Interlisp. BASICS will take you to the Medley Interlisp Project website's Documentation page. Take your time to browse around because chances are the team behind the project has already answered some of the more common questions and curiosities. MANUAL leads to the Interlisp Reference Manual (IRM). Refer to the IRM when you want to know more about certain aspects of Interlisp and when you're ready to move beyond the primer.

<figure><img src=".gitbook/assets/DOCUMENTATION.png" alt=""><figcaption></figcaption></figure>

#### Menus:

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

When interacting with windows, a right-click on the window produces the default contextual menu, which has the following options:

<figure><img src=".gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

| Menu Item | Action                                                                                                                                                                                                            |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Close     | Closes the window, removing it from the screen                                                                                                                                                                    |
| Snap      | Prompts the user for a region on the screen and creates a new window containing a snapshot (bitmap) of the bits currently in that region                                                                          |
| Paint     | Switches to a drawing mode where the cursor acts as a paint brush. The LEFT button adds bits, and the MIDDLE button erases them. The RIGHT button pops up a command menu to change brush options or stop the mode |
| Clear     | Clears the window by erasing all contents within its boundaries and repositions it to the left margin of the first line of text                                                                                   |
| Bury      | Puts the window on the bottom of the occlusion stack, thereby exposing any windows it was previously hiding                                                                                                       |
| Redisplay | Redisplays the window contents                                                                                                                                                                                    |
| Hardcopy  | Prints the contents of the window to the printer or to a file. Used to produce a PDF.                                                                                                                             |
| Move      | Moves the window to a new location specified by pressing and releasing the LEFT mouse button                                                                                                                      |
| Shape     | Allows the user to specify a new region and size for the existing window contents                                                                                                                                 |
| Shrink    | Reduces the window to an icon (a small black rectangle or specialized shape)                                                                                                                                      |
| Expand    | Appears in place of Shrink when the menu is accessed from an icon (shrunken window). It restores the window associated with the icon and removes the icon                                                         |
