# Saving Your Work

Medley's File Manager subsystem manages your code in memory and on disk. As we define and change functions, variables, and data structures, the File Manager keeps track of what we have stored in memory and what has been written to external storage. When we load a file in Medley, it parses all the text in the file as Lisp objects and data structures that are ready in memory for the system to use.  As you change your code and data, you can ask the File Manager to show your changes and store them on disk.

#### For saving and loading our work, essential functions and commands (to be typed in the Exec) are:&#x20;

1.  `(FILES?)`: Displays the functions, variables, and so on we created or changed and asks for directions for each one: add it to an existing file, add it to a new file, or ignore it.  `(FILES?)` does not update the file on disk, but simply logs what should be saved. <br>

    <figure><img src=".gitbook/assets/SAVE ADDER FILE.png" alt="" width="425"><figcaption></figcaption></figure>
2.  `(MAKEFILE 'filename)`: Saves the changes made to a file by writing it to disk. You can now find the file in your current directory.<br>

    <figure><img src=".gitbook/assets/MAKEFILE ADDER FUNCTION.png" alt="" width="433"><figcaption></figcaption></figure>

    We can also call `MAKEFILES` to iterate the `MAKEFILE` operation over a list of files. `MAKEFILES` takes an optional list of files as arguments.  Calling it without arguments - `(MAKEFILES) -`  writes all changes to disk.
3.  `(LOAD 'filename)`: Loads the file `filename` and its definitions.<br>

    <figure><img src=".gitbook/assets/LOAD ADDER FUNCTION.png" alt="" width="406"><figcaption></figcaption></figure>
4.  `FILELST` : A variable that contains all files currently loaded in the environment.<br>

    <figure><img src=".gitbook/assets/FILELIST ADDER FUNCTION.png" alt="" width="407"><figcaption></figcaption></figure>
5.  `filenameCOMS`: Gives a list of all definitions contained in the named file.  For instance, you can see all definitions associated with the file `ADDER-FUNCTION` on the variable `ADDER-FUNCTIONCOMS`.<br>

    <figure><img src=".gitbook/assets/FILENAMECOMS ADDER FUNCTION.png" alt="" width="407"><figcaption></figcaption></figure>

{% hint style="info" %}
You can save multiple Lisp objects to the same file. Try saving all our relevant variables and functions from the previous chapter _(Build Your First Interactive Program)_ to a file! We will use and update this file moving forward.
{% endhint %}



