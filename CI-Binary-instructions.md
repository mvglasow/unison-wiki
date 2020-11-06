# Installing binaries built by the CI process

## GNU/Linux

\todo Write.

## macOS

\todo Write.

After unpacking the tarball, there is a file "unison" which is the text UI and can just be run from the command line.

There is also (future; PR not yet merged) a "Unison.App", but before running it one must do ``xattr -cr /Applications/Unison.app``.  This has been reported to work on 10.14

There is also "unison-gtk", but running it on 10.14 produces:

```
calling unison-gtk2 -version
dyld: Library not loaded:
/usr/local/opt/gtk+/lib/libgtk-quartz-2.0.0.dylib
  Referenced from:
/unison-v2.51.3+ocaml-4.09.1+x86_64.macos-10.15/bin/./unison-gtk2
  Reason: image not found
Abort trap: 6
```

and it is not clear where the gtk build is supposed to come from.

## Windows

\todo Write.

