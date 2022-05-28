# release process

## Release steps
  - Obtain consensus that it's time to release and that non-bugfix changes are on hold
  - LABEL A: Make sure everything builds on all platforms
  - Update NEWS.md
  - Change version number to X.Y.(Z-1)K, for K in .70 .80 90 alpha1 beta1 rc1 etc. 
  - rebuild strings
  - Tag vX_Y_Z_rcN on GitHub, for N starting at 1.  Or don't and point to release artifacts.
  - Announce on unison-users and ask for changes.  Give a deadline, because historically there has been little testing.
  - Evaluate reports and perhaps make changes.
  - If any changes, goto A
  - If no changes, tag the release vZ_Y_Z
  - Announce on unison-users
 
## breaking changes

As of 2.52.0, the plan is to avoid breaking changes in protocol and storage, via versioning.   If there is a breaking change, it definitely requires a new minor version.