# Installing binaries built by the CI process

Before reading this page, see also https://github.com/bcpierce00/unison/wiki/Downloading-Unison

## GNU/Linux

\todo Write.

## macOS

There are two builds.  One builds traditional UNIX tools, and one builds a Mac app.

After unpacking the tarball, there is a file "unison" which is the text UI.  After chmod'ing it to be executable, it can just be run from the command line.
There is also "unison-gtk", which must also be chmod'd to be executable.  It depends on ``/usr/local/opt/gtk+/lib/libgtk-quartz-2.0.0.dylib
``, which is presuming the presence of some particular but currently unknown packaging system.   The wisdom of command-line programs with minimal dependencies is evident :-)

There is also an artifact for "Unison.App".  It is a zip, and within that is a .tar.gz, and within that the App.  Before running it one must do ``xattr -cr /Applications/Unison.app``; otherwise, an unhelpful error message about a damaged app is produced.   This build has been reported to work on 10.14.  However, it failed on 10.13, but that could be due to the same assumption of a particular undocumented packaging system.  See also https://github.com/bcpierce00/unison/issues/469

### Steps to use the binaries
1. Download the macOS build
2. Extract the bin directory
3. Right click on the `unison` binary and select open
4. Confirm that you are okay with running the binary even thought it isn't verified
5. I then had to open a terminal and move the binaries to `/usr/local/bin` so that when running unison over ssh from another host it would find the binaries.

## Windows

\todo Write.

