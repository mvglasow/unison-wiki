# Overview

The product of the unison project is source code.   It can be obtained by git checkout, and tarballs of releases are available at
https://github.com/bcpierce00/unison/releases

In addition there are binaries in various forms:
 - Continuous Integration builds, made available because they are useful
 - packaging systems
 - binaries posted by various people

A standard caution not specific to unison: using binaries requires a determination that the people providing the binaries are trustworthy, and that the process of building them and the hosting infrastructure is safe.  And of course there are similar concerns about source code

# Sources

Sources are available in tarball form at https://github.com/bcpierce00/unison/releases and via git at https://github.com/bcpierce00/unison, Code button.

# Binaries

## Binaries built by github

The unison sources contain CI code, and github builds binaries for a limited number of platforms, available via the "Releases" tab.
  - GNU/Linux is built on Ubuntu, currently 18.04, and will likely work on other x86-64 machines with compatible dependencies.
  - GNU/Linux musl does not have the GUI and is likely more broadly usable.
  - macOS is built on macOS 10.15 with a target of 10.6, and will likely work correctly on earlier versions.
  - Windows is built with mingw, and will likely work on Windows 7 and up.

Note that there are no binaries for most operating systems, and no binaries for most CPU architectures.   Binaries are limited to a small number of OS/CPU combinations, based on what github offers.

See also [CI-built binary installation instructions](https://github.com/bcpierce00/unison/wiki/CI-Binary-instructions).

## Packaging systems

Many packaging systems (including GNU/Linux distributions) provide unison binaries.  These are of varying recency and with varying ocaml versions.

Packaging system binaries are maintained by packaging systems, not the Unison project, and bug reports, complaints about which version is offered, etc. should be addressed to the packaging system, rather than the github issue tracker or unison-users@ mailinglist.

 - Homebrew: macOS users can install Unison from Homebrew by typing "brew install unison".
 - Macports: macOS users can install Unison from Macport (perhaps text UI only).
 - Fink: macOS users can also install Unison by using Fink Commander. Simply download and install Fink Commander, open it and type "Unison" in the search box. Select "Unison-nox" and click install from source. Fink will automatically install all required components.
 - Nix: Unison is included in the standard nixpkgs set for macOS and x86-64 Linux.
 - pkgsrc: unison is packaged as net/unison, and development versions are sometimes available as wip/unison-snapshot.  Supported platforms include NetBSD, DragonflyBSD, Solaris, Darwin, OpenBSD, FreeBSD and also OSF/1, AIX, IRIX and Interix; see here for more information on pkgsrc.
 - FreeBSD: Dan Pelleg has ported unison to FreeBSD. This means that any FreeBSD user with an up-to-date "ports" collection can install unison by doing: cd /usr/ports/net/unison; make && make install. (Make sure your ports collection is fully up to date before doing this, to ensure that you get the most recent Unison version that has been compiled for FreeBSD.)
 - OpenBSD: Unison is included in the standard OpenBSD ports tree, which means that you can install via "pkg_add unison" or build it from source using the standard OpenBSD ports mechanism. See http://www.openbsd.org/faq/faq15.html for information on OpenBSD ports and packages.
 - Debian: There is a Debian package for Unison.
 - Cygwin: Thanks to Andrew Schulman, Cygwin should be able to install unison (text ui only) from the Cygwin setup utility.
 - GODI: Alain Frisch has packaged Unison for distribution via the GODI manager for OCaml packages.
 - Zaurus: The Unison binary from the Debian ARM distribution has been repackaged for Linux PDAs such as the Compaq IPAQ and Sharp Zaurus: See the Zaurus software archives for details.

### Indices

This index is very useful, but incorrectly shows packaging systems as having old versions when there is an rc.

https://repology.org/project/unison/badges

## Binaries provided by other people

The following links are to binaries of unison provided by various people.  They are not produced by the unison project and anyone contemplating use should evaluate their trustworthiness.  (Note that this is not an assertion of untrustworthiness.)

These binaries are maintained by various people, not the Unison project, and bug reports, complaints about which version is offered, etc. should be addressed to them, rather than the github issue tracker or unison-users@ mailinglist.

Only recent  unison versions built with recent ocaml are listed.  This means at least 2.53.0 and 4.11.

 - built in [OBS unison](https://build.opensuse.org/project/show/Archiving:unison) for a large number of distributions with [OCaml 4.14.0](https://build.opensuse.org/package/show/Archiving:unison:buildrequires/ocaml), published here: [https://download.opensuse.org/repositories/Archiving:/unison/](https://download.opensuse.org/repositories/Archiving:/unison/)
     * In case a pre-release exists for testing, it is also built in [OBS unison:next](https://build.opensuse.org/project/show/Archiving:unison:next), and published here: [https://download.opensuse.org/repositories/Archiving:/unison:/next](https://download.opensuse.org/repositories/Archiving:/unison:/next)
 - [Arch docker container](https://github.com/AlterDepp/unison-docker)
