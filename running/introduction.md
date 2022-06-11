In the 1980s Lisp workstations were an important development. A portable version of one of those environments was created at that time called Medley. The source code to that original system has been made open-source, ported, and modernized, and is available on GitHub. This introduction is about that system.

Medley originally supported Interlisp (an older dialect of Lisp) but grew to support Common Lisp as well.

The Medley development environment is very different from the file-based model used today. The value of this system is to provide the ability to learn about, explore, and possibly utilize these benefits in future projects.

The majority of the system is written in Lisp and rides on a portable virtual machine written in portable C. The system uses an X11 window to display the bitmap in which the Lisp code manages. The system is very portable and has been ported to Linux, Macintosh, and other systems.

The purpose of this Introduction is to provide access to this system to someone who is already familiar with current Common Lisp development environments in as brief a form as possible.

## Architecture

The Medley system operates in a virtual machine.  Lisp code is either
interpreted or compiled into byte-code for this virtual
machine.  The use of a virtual machine in this way, while popular
today with environments such as Java and C#, was quite a bit more
unique and innovative when Medley was developed.  As it does with
other languages, the use of a virtual machine made Medley portable.

The Medley system is comprised of two major pieces.  The first part is
the virtual machine.  This is called "maiko".  The remainder of the
system is written in a combination of Interlisp and Common Lisp.

Medley is both image-based (like Smalltalk) and
file-based (like most other systems such as C, Java, C#, Python,
etc.). 

In a file-based system, source code resides in files.
Interpreters interpret this code and compilers convert these files
into machine code (placed in other files) for execution.  Development
is done by editing the source files, compiling, and loading.

In an image-based system, you are working on a live, running system.
As code is written, the running system evolves.  At various points,
the user can save an image of that running system.  What that is
is a single, binary, copy of the entire running system.  It basically
saves the state of the running machine at the point the image is
saved.  Later, the system may be restarted with a particular image
and the system resumes from the exact point from which it was saved.

In Medley Interlisp, files are used to save code and load it back,
but development happens in the same image as it is running. This
allows development to proceed without having to switch contexts from editing
source code to running that code or compiling it. Code is formatted
("pretty-printed") automatically, with the user freed from worrying
about maintaining indentation, parenthesis matching, and other syntactic
constraints. When you want to see or change something, the entire system is at your
immediate disposal.  You do not need to search for the source files.
Also, changes that you make take effect immediately.  There is no need
to rebuild and redeploy the system.

As opposed to having two language sub-systems (Interlisp and Common
Lisp), Medley integrates the two such that both or either can be used.
Interlisp functions as the "Interlisp" (abbrev "IL") package of Common Lisp.

------------
_Many thanks to [Blake McBride](https://github.com/blakemcbride) and his [Medley Intro](https://github.com/blakemcbride/medley-intro) from which this was taken._