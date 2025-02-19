# Installing binaries built by the CI process

Before reading this page, see also https://github.com/bcpierce00/unison/wiki/Downloading-Unison

Before reporting an issue about the CI binaries or anything, please thoroughly read and understand https://github.com/bcpierce00/unison/wiki/Reporting-Bugs-and-Feature-Requests

Each CI build has been done on a particular operating system version.  There is no expectation that a build will run on a previous version, and even running on a later version depends on that operating system's compatibility support.  Note that "Linux" is not an operating system, and that at present CI artifacts are produced for Ubuntu, because that's what github provides.

## GNU/Linux

As an example, the file `unison-2.53.3-ubuntu-x86_64-static.tar.gz` contains
```
 -rw-r--r--    root/root      35147 LICENSE
 -rw-r--r--    root/root       6916 README.md
 drwxr-xr-x    root/root          0 bin/
 -rwxr-xr-x    root/root    3065536 bin/unison
 -rwxr-xr-x    root/root    1109952 bin/unison-fsmonitor
 -rw-r--r--    root/root     214126 unison-manual.html
 -rw-r--r--    root/root     363952 unison-manual.pdf
 -rw-r--r--    root/root     157212 unison-manual.txt
```

\todo Explain if `unison` is dynamically linked and if so, what it expects.

## macOS

There are two builds.  One builds traditional UNIX tools, and one builds a Mac app.  Both are currently built on 10.15, and also seem targetted at 10.15.

After unpacking the tarball, there is a file "unison" which is the text UI.  After chmod'ing it to be executable, it can just be run from the command line.
There is also "unison-gtk", which must also be chmod'd to be executable.  It depends on ``/usr/local/opt/gtk+/lib/libgtk-quartz-2.0.0.dylib
``, which is presuming the presence of some particular but currently unknown packaging system.   The wisdom of command-line programs with minimal dependencies is evident :-)

There is also an artifact for "Unison.App".  It is inside a `.app.tar.gz`.  Before running it one must do ``xattr -cr /Applications/Unison.app``; otherwise, an unhelpful error message about a damaged app is produced.   This build has been reported to work on 10.14.  However, it failed on 10.13, but that could be due to the same assumption of a particular undocumented packaging system.  See also https://github.com/bcpierce00/unison/issues/469

### Steps to use the binaries
1. Download the macOS build
2. Extract the bin directory
3. Right click on the `unison` binary and select open
4. Confirm that you are okay with running the binary even thought it isn't verified
5. I then had to open a terminal and move the binaries to `/usr/local/bin` so that when running unison over ssh from another host it would find the binaries.

## Windows

\todo Write.

