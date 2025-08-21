# Drawing in Medley

In _Build Your First Interactive Program,_ we learnt how to make our own windows. In Medley, we can create a special window for drawing, somewhat similar to a pixel art editor- a bitmap editor. A bitmap is a rectangular array of pixels.

The form `(BITMAPCREATE width height)` creates a bitmap in the background but cannot be seen till we assign a variable name to it and edit it. We can edit a bitmap using:

`(EDITBM bitmap-name)`

In an Exec, type:

`(SETQ my.bitmap (BITMAPCREATE 40 40))`

and then:

`(EDITBM my.bitmap)`

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Your cursor will now display the outline of the window you created. Your Prompt Window displays: _Indicate the position for the Bitmap Edit Window_. Left-click on an empty space in your workspace to place your bitmap editor.\


<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

To draw, hold down on your left mouse button and to erase hold down your middle mouse button.

To save your bitmap, hold down the middle mouse button in the solid gray box in the upper-center area. A menu will appear. While holding down the middle mouse button place your cursor on top of "OK" and let go. Your work will be saved and the window will close. The next time you edit your bitmap, you'll see what you previously drew.

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
