# Saving Your Work

Medley's File Manager subsystem is content-aware. It can do more than just save files. As we define and change functions, variables, and data structures, the File Manager keeps track of what we have stored in temporary session memory and what has already been written and not written to a file in permanent, external storage. Modern file managers use separate, dedicated programs to process the content of a file. In contrast, when we load a file in Medley, it parses all the text in the file as Lisp objects and data structures that are ready in memory for the system to use. Consider Medley's File Manager a smart, live memory monitor of sorts.

#### For saving and loading our work, essential functions and commands (to be typed in the Exec) are:&#x20;

1.  `(FILES?)`: Gives a list of objects we created and changed that can be "dumped"/written to a file, and asks for directions. This does not update the actual file in storage- it logs what needs to be saved eventually. <br>

    <figure><img src=".gitbook/assets/SAVE ADDER FILE.png" alt="" width="425"><figcaption></figcaption></figure>
2.  `(MAKEFILE 'filename)`: Writes and saves the changes made to a file in storage. You can now find the file in your storage path.<br>

    <figure><img src=".gitbook/assets/MAKEFILE ADDER FUNCTION.png" alt="" width="433"><figcaption></figcaption></figure>

    We can also use MAKEFILES to iterate the MAKEFILE operation over a list of files. MAKEFILES takes a list of files.
3.  `(LOAD 'filename)`: Loads the file and all its objects. Use this when you start a new Medley session.<br>

    <figure><img src=".gitbook/assets/LOAD ADDER FUNCTION.png" alt="" width="406"><figcaption></figcaption></figure>
4.  `FILELST` : Gives a list of all files currently loaded in the environment.<br>

    <figure><img src=".gitbook/assets/FILELIST ADDER FUNCTION.png" alt="" width="407"><figcaption></figcaption></figure>
5.  `filenameCOMS`: Gives a list of all Lisp objects in the filename specified. <br>

    <figure><img src=".gitbook/assets/FILENAMECOMS ADDER FUNCTION.png" alt="" width="407"><figcaption></figcaption></figure>

{% hint style="info" %}
You can save multiple Lisp objects to the same file. Try saving all our relevant variables and functions from the previous chapter _(Build Your First Interactive Program)_ to a file! We will use and update this file moving forward.
{% endhint %}



