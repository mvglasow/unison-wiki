# Source

Unison is primarily released as source.  See https://github.com/bcpierce00/unison/releases for the latest release.

# Binaries

## Binaries built by github

The unison sources contain CI code, and github builds binaries for a number of platforms, available at the link above.

  - Linux is built on Ubuntu, currently 18.04, and will likely work on other x86-64 machines with compatible dependencies.
  - Linux musl does not have the GUI and is likely more broadly usable.
  - macOS is built on macOS 10.16, and will likely only work on that version.
  - Windows is built with mingw, and will likely work on Windows 7 and up.

Note that there are no binaries for most operating systems, and no binaries for most CPU architectures.   Binaries are limited to a small number of popular OS/CPU combinations, based on what github offers.

## Packaging systems

Many packaging systems (including GNU/Linux distributions) provide unison binaries.  These are of varying recency and with varying ocaml versions.

## Binaries provided by other people

The following links are to binaries of unison provided by various people.  They are not produced by the unison project and anyone contemplating use should evaluate their trustworthiness.  (Note that this is not an assertion of untrustworthiness.)

If the web page does not have the latest release compiled with a recent ocaml version (defined as >= 4.09), it will be marked as OLD.

### Multi-OS sources

#### inria

http://unison-binaries.inria.fr/ (OLD)

### GNU/Linux

#### SUSE

https://build.opensuse.org/package/show/devel:languages:ocaml/unison (OLD)

#### Debian

https://www.preining.info/blog/2020/04/working-unison-for-debian/ (OLD)
