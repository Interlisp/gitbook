# The File Browser

The file browser is a dedicated tool inside Medley that acts as a file manager. From the background menu, select File Browser. Hold down the left mouse button and drag to create the following window:

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

To view all the files in a directory, type \* and press Enter, in the File group description prompt:

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

You can also type a specific file name to work only with that one.

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

To select a file, use the left mouse button; to select multiple, use the middle mouse button. A file is selected when a solid right-pointing arrow appears to its left. To unpick an already chosen file, hold down the Ctrl/Command key while pressing the middle mouse button.

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Once one or more files have been selected, you can perform the operations available to you through the permanent menu FB Commands attached on the right.

| Command   | What Does it Do                                                                                                                |
| --------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Delete    | Marks selected files for deletion (crossed out in the list). Files aren’t removed until you use Expunge.                       |
| Undelete  | Restores any files previously marked for deletion.                                                                             |
| Copy      | Copies selected files. You’ll be prompted for a full destination filename (for one file) or a directory (for multiple).        |
| Rename    | Moves or renames selected files. You’ll be prompted, for a new filename (single) or a target directory (multiple).             |
| Hardcopy  |                                                                                                                                |
| See       | Opens the selected file in a new read-only window for viewing.                                                                 |
| Edit      | Opens the selected file in the Medley editor. For Lisp files, only the `FILECOMS` list (functions, variables, etc.) is edited. |
| Load      | Loads selected file(s) into the Medley environment.                                                                            |
| Compile   | Compiles selected file(s) from disk. If changes were made, use `(MAKEFILE 'filename)` before compiling.                        |
| Expunge   | Permanently deletes all files currently marked for deletion.                                                                   |
| Recompute | Refreshes the directory listing to reflect any recent changes (e.g., new file versions).                                       |

