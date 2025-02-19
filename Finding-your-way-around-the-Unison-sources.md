# TODO: Change ROADMAP.txt to ROADMAP.md and move markup, deleting this copy

**This page is a marked up but otherwise wholesale import of src/ROADMAP.txt.**

Although parts of it are somewhat intricate, Unison is not a very large
program.  If you want to get familiar with the code, the best place to
start is probably with the textual user interface module, [uitext.ml](https://github.com/paulp/unison/blob/master/src/uitext.ml).  The
'start' function at the bottom is a simple driver for all the rest of the
major modules in the program.  (See below for some more details.)

After that, check out [main.ml](https://github.com/paulp/unison/blob/master/src/main.ml) to see how things get set up.  Again,
the bottom is the most interesting part.

Next, look at the interface files in this order:
```
globals.mli      common low-level datatype definitions
common.mli       common high-level datatype definitions
update.mli       update detection
recon.mli        reconciliation of updates (i.e. deciding what to do)
transport.mli    propagation of changes (also files.mi)
```
From here, you probably know your way around enough to decide where to
look next.  Here's a summary of the most interesting modules:
```
pred          implements "predicates" (e.g. ignore) based on regexps
prefs         command-line and preference file parsing
main          the top-level program
os            low-level filesystem operations
trace         tracing messages
uicommon      stuff common to the two UIs
uitext        the textual UI
uigtk         the graphical UI (Gtk version)
```

The files [linktext.ml](https://github.com/paulp/unison/blob/master/src/linktext.ml) and [linkgtk.ml](https://github.com/paulp/unison/blob/master/src/linkgtk.ml) contain linking commands for
assembling Unison with either a textual or a graphical user interface.
(The Main module, which takes the UI as a parameter, is the only part of
the program that is functorized.)

The module Remote handles RPC communication between clients and remote
servers.  It's pretty tricky, but the rest of the system doesn't need
to know much about how it works.

                   ________________________________

In a little more detail, here is the flow of control at startup time:

- The first code to execute (not counting some small per-module
  initialization stuff) is the call to Main.init() from Main.Body.  This
  handles a few special preferences like -version, -doc, and -server.  If it
  returns, then Main.Body next calls the start function of whatever UI
  module has been provided as an argument to the Main module.

- The start function in each of the UI modules (Uitext, Uigtk2, etc.)
  behaves slightly differently, but they all have quite a bit of common
  structure; this is captured in the function Uicommon.uiInit, which is
  where all the heavy lifting happens (parsing command line and preference
  files, connecting to the server, etc.); when this returns, the user
  interface continues with the actual synchronization.

- The core functions that do the real work (of synchronization) are:
```
Update.findUpdates()     find out what changed
Recon.reconcileAll       build the list of "recon items"
Transport.transportItem  perform the action described by a recon item
```