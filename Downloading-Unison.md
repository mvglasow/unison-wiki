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

Packaging system binaries are maintained by packaging systems, not the Unison project, and bug reports, complaints about which version is offered, etc. should be addressed to the packaging system, rather than the github issue tracker or unison-users@ mailinglist.

 - Homebrew: OS X users can install Unison from Homebrew by typing "brew install unison".
 - Macports: OS X users can install Unison from Macport (perhaps text UI only).
 - Fink: OS X users can also install Unison by using Fink Commander. Simply download and install Fink Commander, open it and type "Unison" in the search box. Select "Unison-nox" and click install from source. Fink will automatically install all required components.
 - pkgsrc: pkgsrc packages are available for recent versions of unison as net/unisonV.VV. Supported platforms include NetBSD, DragonflyBSD, Solaris, Darwin, OpenBSD, FreeBSD and also OSF/1, AIX, IRIX and Interix; see here for more information on pkgsrc.
 - FreeBSD: Dan Pelleg has ported unison to FreeBSD. This means that any FreeBSD user with an up-to-date "ports" collection can install unison by doing: cd /usr/ports/net/unison; make && make install. (Make sure your ports collection is fully up to date before doing this, to ensure that you get the most recent Unison version that has been compiled for FreeBSD.)
 - OpenBSD: Unison is included in the standard OpenBSD ports tree, which means that you can install packages or build it from source using the standard OpenBSD ports mechanism. See http://www.openbsd.org/faq/faq15.html for information on OpenBSD ports and packages.
 - Debian: There is a Debian package for Unison.
 - Cygwin: Thanks to Andrew Schulman, Cygwin should be able to install unison (text ui only) from the Cygwin setup utility.
 - GODI: Alain Frisch has packaged Unison for distribution via the GODI manager for OCaml packages.
 - Zaurus: The Unison binary from the Debian ARM distribution has been repackaged for Linux PDAs such as the Compaq IPAQ and Sharp Zaurus: See the Zaurus software archives for details.

## Binaries provided by other people

The following links are to binaries of unison provided by various people.  They are not produced by the unison project and anyone contemplating use should evaluate their trustworthiness.  (Note that this is not an assertion of untrustworthiness.)

These binaries are maintained by various people, not the Unison project, and bug reports, complaints about which version is offered, etc. should be addressed to them, rather than the github issue tracker or unison-users@ mailinglist.

If there is a link, but it does not have the latest release compiled with a recent ocaml version (defined as >= 4.09), it will be marked as OLD.

 - http://unison-binaries.inria.fr/ (OLD)
 - https://build.opensuse.org/package/show/devel:languages:ocaml/unison (OLD)
 - https://www.preining.info/blog/2020/04/working-unison-for-debian/ (OLD)
 - Generic linux: Zbigniew Diaczyszyn has built an x86_64 binary for Unison on Slackware 14.0.
 - ARM Linux: Jens Wagner has compiled a static binary (text only) for the ARM Linux platform
