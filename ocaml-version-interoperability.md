* Introduction

Before version 2.52.0, unison's wire protocol depended on the ocaml version.   In 2.52.0 there is a new wire protocol, used if both sides are 2.52.0 or later, that does not depend on the ocaml version.

This page attempts to collect information about which ocaml versions work with which other versions, when using the 2.51 wire protocol.   When 2.52.0 is released, users should upgrade and this information should become irrelevant.

* Interoperability Table

|old|new|sync-unchanged|sync|archive
| :- | :- | :- | :- | :- |
|4.09|4.11|ok|FAIL| ok? |
|4.08|4.11|ok|FAIL| ? |
|4.08|4.09|ok|ok| | ? |

