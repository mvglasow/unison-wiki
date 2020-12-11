* Introduction

unison's wire protocol depends on the ocaml version; see https://github.com/bcpierce00/unison/issues/375

However, when there is a mismatch and an actual change in serialization format, some operations can succeed while others fail.
This page attempts to collect information about which versions work with which other versions.

* Interoperability Table

|old|new|sync-unchanged|sync|
| :- | :- | :- | :- |
|4.09|4.11|ok|FAIL|

