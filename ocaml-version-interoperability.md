# Introduction

Before version 2.52.0, unison's wire protocol depended on the ocaml version.   In 2.52.0 there is a new wire protocol, used if both sides are 2.52.0 or later, that protocol does not depend on the ocaml version.  Thus, there is no need to use unison with matching ocaml versions.

# Interoperability Table

This section collects information about unison interoperability when built with differing ocaml versions, when using the 2.51 wire protocol.   When 2.52.0 is released, users should upgrade and this information should become irrelevant.

|old|new|sync-unchanged|sync|archive
| :- | :- | :- | :- | :- |
|4.09|4.11|ok|FAIL| ok? |
|4.08|4.11|ok|FAIL| ? |
|4.08|4.09|ok|ok| | ? |

# Surveys

This section contains data from surveying the Unison user community about ocaml versions in use.  Generally, these are done in order to understand the consequences of desupporting old ocaml versions.  Note that this different that "avoiding desupporting a version that anyone is using".

## On the nature of LTS

Running an LTS system is a choice to use old software that receives important fixes only (backported by the LTS provider).  Additionally, some LTS users expect to build new unison releases with the dependencies as provided by their LTS system.  Unison as a project does not provide support for the LTS environment.  Instead, we only address issues in the latest release, and document the dependencies.   Thus as an example "unison 2.53.0 needs ocaml 4.08 but LTS Foo version X has ocaml 4.07" is not a bug in unison.

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

The rough conclusion, between the difficulty of supporting old versions and the bulk of the usage, was that moving 4.08 as a minimum version is a reasonable next step.  Thus 2.53.0 will require ocaml 4.08 or greater.

