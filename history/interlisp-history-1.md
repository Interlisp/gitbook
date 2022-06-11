# Interlisp History

Interlisp History (draft)

(Originally copied from [https://interlisp.org/saved.html#history](https://interlisp.org/saved.html#history)) and [https://interlisp.org/new.html#interlisp-history](https://interlisp.org/new.html#interlisp-history). It was intended to be merged with [Interlisp History and Timeline](https://docs.google.com/document/u/0/d/1QXUMQ0OUttYYzWUvgdVcnkz5Gym\_t1MDnMT8XZJe-NI/edit)) but we started to work on the Zotero bibliography instead.

Interlisp (a programming environment) was built around the programming language Lisp, known as the second oldest programming language in use (FORTRAN being the oldest). Interlisp had its roots in the development of an interactive Lisp system for the _Digital Equipment Corporation’s PDP-10_, in 1966 by _Danny Bobrow_ and _D. L. Murphy_ at Bolt-Beranek and Neuman (currently known as BBN Technologies) in Boston.

In 1970, when Danny Bobrow and Warren Teitelman moved to Xerox Palo Alto Research Center (PARC) BBN LISP was renamed “Interlisp”. Interlisp was popular in the AI industry because of its easy-to-integrate interactive development tools such as debuggers, simple auto-correction, and analysis tools. Defense Advanced Research Projects Agency (DARPA) funded the development to support researchers in Artificial Intelligence, who chose LISP over Fortran for symbolic computing.

When PARC built the Xerox Alto and its subsequent working stations called the D-machines, the development of Interlisp was directed towards supporting all the internal users. Researchers were developing the idea of using the Alto with such a machine architecture that could support more compact programs by assistance of microcoded processors that would interpret byte-coded instruction sequences smoothly. Mesa, Cedar, Smalltalk, and Interlisp were used as separate languages/virtual machines for this purpose.

However, the Alto was too memory-constrained for using Lisp. To run Lisp, the D machines were used as they had their own different microcode and engines, which were implemented by different people. The names and their respective coders are mentioned below:

* Dandelion _(aka Xeros 1108)_ by Steve Purcell
* Dolphin _(aka Xeros 1100)_ by Alan Bell
* Dorado _(aka Xeros 1132)_ by Willie-Sue Haugeland and Larry Masinter
* Daybreak _(aka Xeros 1186)_ by Don Charnley

The software was called Interlisp-D. The releases for the Interlisp-D were named alphabetically, starting with Allegro, Bravo, Carol, D\[?], E\[?], Fugue, G\[?] Harmony, Intermezzo, Jazz, Koto, Lyric, Medley. This software was implemented initially in Interlisp. Later, the programmers could freely use Interlisp in conjunction with Common Lisp by using a common Virtual Machine. After the latest release, the whole system was renamed _“Medley”_.

**Copyright Narrative**

Interlisp was developed at BBN and Xerox in the early 70s, with the understanding at the time that the results were considered to be public domain because of ARPA fundings. There were no copyright claims to Interlisp at that time.

Later, a feature was introduced to the system, to insert a copyright notice of the developer’s choice automatically in Lisp source files when they were edited. Since then, the development of Interlisp has continued through commercialization and release by copyrights to _“Xerox Artificial Intelligence Systems (XIAS)”_ .

In the mid-80s, a spin-out was started and XIAS was incarnated into a separate corporation known as _"Envos"_ , and several employees left Xerox to join Envos. In 1990, Envos shut down with a relatively short lifespan. Then, John Sybalsky started a new company called _“Venue”_ as a smaller venture based on porting Maiko to other machines and OS. Wayne Marci (John Sybalsky’s stepson) inherited all the assets of Venue in 2019.

Paul McJones has gathered all files from Xerox PARC for Interlisp releases for the Computer History Museum (CHM). The _"CHM collection"_ represents snapshots of the code from a time when the intellectual property rights were clear (i.e., Xerox owned everything at the time of the snapshot(s), and gave permission to CHM to display and distribute it). This leads to an opportunity for curating the code, and perhaps creating a new execution environment from it (e.g., _Josh Dersh’s Darkstar emulator_ ).

Later, Wayne Marci permitted the use of Venue’s code and license to release the software as open-source, which should be consistent and compliant with Venue's license.

#### REFERENCES (These belong in the bibliography) <a href="#_3mknv06c5qet" id="_3mknv06c5qet"></a>

* Paul McJones. Interlisp Family: [_**History of Lisp including Interlisp-D**_](http://www.softwarepreservation.org/projects/LISP/interlisp\_family#Interlisp-D\_)
* INTERLISP - WIKIPEDIA: [_**Wikipedia article for Interlisp**_](https://en.wikipedia.org/wiki/Interlisp)
* Richard R. Burton, Ronald M. Kaplan, Larry M. Masinter, _Papers on Interlisp-D_, Xerox Corporation 1980; 1981. [_**PDF**_](http://www.softwarepreservation.net/projects/LISP/interlisp-d/Papers\_On\_Interlisp-D.pdf)
* Warren Teitelman’s: [_**History of Interlisp**_](https://dl.acm.org/profile/81339532165)
* L. Peter Deutsch, Xerox Corporation, Palo Alto Research Center (PARC) Palo Alto, California 94304. [_**A LISP Machine with Very Compact Programs**_](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.109.6660)
* Older version of INTERLISP: [_**PDP-10/INTERLISP-10**_](https://github.com/PDP-10/Interlisp-10)
* Beau Sheil, 1983: [_**Power Tools for Programmers**_](https://www.oreilly.com/library/view/readings-in-artificial/9780934613125/xhtml/B9780934613125500483.xhtml)
* Photos from IJCAI 1982 Announcing sale of Dorado and Dandelion: [_**Interlisp-D at AAAI-82**_](https://photos.app.goo.gl/826EbhnkQSl8rePE3)
* PDF files at CHM: [_**Interlisp-D**_](http://bitsavers.org/pdf/xerox/interlisp-d/) _and_ [_**Interlisp**_](http://bitsavers.org/pdf/xerox/interlisp/)
* Maiko files at: [_**GitHub Maiko**_](https://github.com/Interlisp/maiko)
* Lisp and other files soon to be at: [_**GitHub Medley**_](https://github.com/Interlisp/medley) (available on DropBox and iCloud temporarily.)
* Article at Introducing Darkstar: A Xerox Star Emulator: [_**DarkStar Dandelion hardware emulator**_](https://github.com/livingcomputermuseum/Darkstar) (can be used to run older sysouts)

**Informative Documents**

* (1986) **CommonLoops: merging Lisp and object-oriented programming**, OOPLSA '86. Conference proceedings on Object-oriented programming systems, languages and applications
* (1983) **1983 Interlisp Reference Manual** (one of many editions)
* (1982) Richard P. Gabriel, Larry Masinter. [**Performance of Lisp Systems.**](http://portal.acm.org/citation.cfm?id=802143) ACM Symposium on LISP and Functional Programming.
* (1981) Warren Teitelman, Larry Masinter. _**The Interlisp Programming Environment**._ IEEE Computer, April 1981.
* [**Selling Lisp machines \~1980**](https://larrymasinter.net/stefik-loops.pdf).
* (1980) [_**Global Program Analysis in an Interactive Environment**_](https://larrymasinter.net/thesis.pdf) _(Larry's PhD thesis)._
* (1980) **Overview and Status of DoradoLisp**, 1980 Lisp conference.
* (1980) Larry Masinter, L. Peter Deutsch. **Local Optimization in a Compiler for Stack-Based Lisp Machines.** Lisp Conference. Stanford University.
* (1988) [**Common LISP Cleanup**](http://www.softwarepreservation.org/projects/LISP/conference/iwoleas88/Masinter-CommonLispCleanup.pdf). A description of the process of "cleaning up" the Common Lisp standard. See [**Wikipedia article**](http://en.wikipedia.org/wiki/X3J13#Cleanup\_subcommittee) and [**cleanup proposal template**](https://larrymasinter.net/cl-cleanup-proposal.txt).
* (1985) [**AI Systems and Technologies**](https://larrymasinter.net/85-ai-tutorial.pdf), (initial part of) a 2-day tutorial. Page 4 is still true: "AI is a goal, not a fact".
