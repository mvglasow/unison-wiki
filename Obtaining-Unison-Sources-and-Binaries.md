# Overview

The product of the unison project is source code.   It can be obtained by git checkout, and tarballs of releases are available at
https://github.com/bcpierce00/unison/releases

In addition there are binaries in various forms:
 - Continuous Integration builds, done for CI purposes, but also made available
 - packaging systems
 - binaries posted by various people

A standard caution not specific to unison: using binaries requires a determination that the people providing the binaries are trustworthy, and that the process of building them and the hosting infrastructure is safe.  (There are similar concerns about source code.)

# Sources

Sources are available in tarball form at https://github.com/bcpierce00/unison/releases and via git at https://github.com/bcpierce00/unison, Code button.

# Binaries

## Binaries built by CI

The unison sources contain CI code, and project CI (github GHA at the moment) builds binaries for a limited number of platforms, available via the "Releases" tab.
  - Ubuntu is probably 20.04, and will likely work on other x86-64 machines with compatible dependencies.
  - macOS is built on macOS 10.15 with a target of 10.6, and will likely work correctly on earlier versions.
  - Windows is built with mingw, and will likely work on Windows 7 and up.

Generally, these artifacts contain not only the unison executable but also the manual.

Note that there are no binaries for most operating systems, and no binaries for most CPU architectures.   Binaries are limited to a small number of OS/CPU combinations, based on what github offers.

See also [CI-built binary installation instructions](https://github.com/bcpierce00/unison/wiki/CI-Binary-instructions).

## Packaging systems

Many packaging systems (including GNU/Linux distributions) provide unison binaries.  These are of varying recency and with varying ocaml versions.  Packaging systems generally should provide the documenation as well; this is highly variable in practice.

Packaging system binaries are maintained by packaging systems, not the Unison project, and bug reports, complaints about which version is offered, etc. should be addressed to the packaging system, rather than the github issue tracker or the unison-users@ mailinglist.  This list does not attempt to give or duplicate documentation for each packaging system; it assumes familiarity with the packaging system and simply points to where unison is located within it.  Packaging systems are listed in decreasing order of portability, and then by OS, with proprietary systems later.

 - [pkgsrc](https://www.pkgsrc.org) (NetBSD, illumos, and almost every even semi-maintained platform except Windows): Release present as net/unison, and development snapshot as wip/unison-snapshot.
 - Nix (x86-64 Linux and macOS): Present.
 - most GNU/Linux distributions: Present as unison.
 - FreeBSD ports: Present as net/unison
 - OpenBSD ports: Present as unison.
 - Homebrew (macOS only): Present as unison.
 - Macports (macOS only): Perhaps TUI only.
 - Fink (macOS only): Present as "Unison-nox".
 - Cygwin (Windows only): Present as unison, perhaps TUI only.
 
### Indices

This index is very useful, but incorrectly shows packaging systems as having old versions when there is an rc.

https://repology.org/project/unison/badges

## Binaries provided by other people

The following links are to binaries of unison provided by various people.  They are not produced by the unison project and anyone contemplating use should evaluate their trustworthiness.  (Note that this is not an assertion of untrustworthiness.)

These binaries are maintained by various people, not the Unison project, and bug reports, complaints about which version is offered, etc. should be addressed to them, rather than the github issue tracker or unison-users@ mailinglist.

Only reasonably up-to-daet unison versions built with a maintained version of ocaml are listed.  This means a Unison version that is either the most recent release or was the most recent release some time in the last 90 days.

 - built in [OBS unison](https://build.opensuse.org/project/show/Archiving:unison) for a large number of GNU/Linux distributions with [OCaml 4.14.0](https://build.opensuse.org/package/show/Archiving:unison:buildrequires/ocaml), published here: [https://download.opensuse.org/repositories/Archiving:/unison/](https://download.opensuse.org/repositories/Archiving:/unison/)
     * In case a pre-release exists for testing, it is also built in [OBS unison:next](https://build.opensuse.org/project/show/Archiving:unison:next), and published here: [https://download.opensuse.org/repositories/Archiving:/unison:/next](https://download.opensuse.org/repositories/Archiving:/unison:/next)
 - [Arch docker container](https://github.com/AlterDepp/unison-docker) - OLD, pending removal from this page.  See https://github.com/AlterDepp/unison-docker/issues/1

