(See [Medley repo README](https://github.com/Interlisp/medley/#readme) for instructions on getting Medley.
Make sure you have an X-server running to manage the Medley Interlisp display, and the DISPLAY environment variable set to point to your X-server.

Running Medley can be done by typing:
```
$ cd medley
$ ./run-medley
```

Or, if you wish to start Medley up with a particular image file (SYSOUT):

```
$ cd medley
$ ./run-medley <SYSOUT-file-name>
```
The first time the system is run it loads the system image that comes
with the system.  When you exit the system (or "do a `SaveVM`" menu option)
the state of your machine is saved
in a file named `~/lisp.virtualmem`.  Subsequent system startups 
load the `~/lisp.virtualmem` image by default.

### Exiting The System

The system may be exited from an Interlisp prompt by typing:

```
(LOGOUT)
```

Or from a Common Lisp prompt with:
```
(IL:LOGOUT)
```
When you logout of the system, Medley automatically creates a binary
dump of your system located in your home directory named
``lisp.virtualmem''. The next time you run the system, if you don't
specify a specific image to run, Medley restores that image so that
you can continue right where you left off.

