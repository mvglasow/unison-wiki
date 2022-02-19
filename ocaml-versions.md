# ocaml versions relevant to unison

As of 2.52.0, one will not need matching ocaml versions.   Thus there is a future question about the consquences of removing support for old ocaml in unison beyond 2.52.0.

## On the nature of LTS

Running an LTS system is a choice to use old software that receives important fixes only (backported by the LTS provider).  Additionally, some LTS users expect to build new unison releases with the dependencies as provided by their LTS system.  Unison as a project does not provide support for the LTS environment.  Instead, we only address issues in the latest release, and document the dependencies.   Thus as an example "unison 2.53.0 needs ocaml 4.08 but LTS Foo version X has ocaml  4.02" is not a bug in unison.

## February 2022 survey
```
4.13    9
4.12    6
4.11    9       obviously most are on 4.11 or higher: 24 votes
4.10    4
4.09    0       a clue that 4.09 and below have mostly aged out, except for LTS
4.08    6       some kind of LTS?
4.07    1
4.06    1       FreeBSD ports 2022
4.05    4       FreeBSD ports older, RHEL 8 (beta in 2018)
4.02    1
```
