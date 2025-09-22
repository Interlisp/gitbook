# Making a Graph with Grapher

Grapher is a small program for making graphs in Medley. There are a few ways to do that but for now we'll stick to the easiest method.&#x20;

The function SHOWGRAPH displays graphs and allows you to edit them. The parameters of SHOWGRAPH are:

`(SHOWGRAPH graph window lefibuttonfn middlebuttonfn topjustifyflg alloweditflg copybuttoneventfn)`

We won't go over what all the parameters do in this primer. Instead, let's try making our first graph.&#x20;

Start by declaring a variable name. In an Exec, type:

`(SETQ my.graph NIL)`

Now let's create a window which will serve as a graph editor:

`(SHOWGRAPH my.graph "My Graph" NIL NIL NIL T)`

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Place your graph on an empty space. If you want to change the size and shape of the window, hold down the right mouse button on the title bar just like you would with any window, place your cursor on the menu item Shape and let go.

Let's start building our graph by adding and connecting nodes. In the white space in the graph editor window, hold down your right mouse button and a different menu will appear with context-relevant options to choose from.

<figure><img src=".gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Select Add Node, and you'll see a small window appear on top of the graph window with the title Node label?

<figure><img src=".gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

This is the label of your node. Type Node ONE for now and press Enter. You'll see a node attached to your cursor. To place the node, left-click on any empty space in the window. Your node will appear with the label you set.

<figure><img src=".gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Add three more nodes with the labels One A, One B and One C respectively.

<figure><img src=".gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

Let's link these nodes. Bring up the main menu for the graph window and select Add Link.

<figure><img src=".gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

Once you select Add Link by placing the mouse cursor on top of it and letting go, you'll notice your Prompt Window is asking From?

<figure><img src=".gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

Left-click on the node from which the link will be drawn.

Your Prompt Window will now ask To?

Left-click on the node to which the link will be drawn.

Your Prompt Window now tells you which link you just added.

<figure><img src=".gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

You'll notice a straight line from Node ONE to ONE A in your graph window. Add two more links from Node ONE to ONE B and to ONE C.

<figure><img src=".gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

You can also move and delete nodes. To move a node, select Move Node from the menu. Once the menu disappears, hold down left mouse button on the node you want to move, drag it to a new location and let go.&#x20;

To delete a node, select Delete from the menu and then the node to be deleted.

{% hint style="info" %}
Your prompt window always displays relevant information to whatever you're trying to do. If you're unsure how to proceed, look at the prompt window for instructions.
{% endhint %}
