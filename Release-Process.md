# release process

## Release steps
  - Obtain consensus that it's time to release and that non-bugfix changes are on hold
  - LABEL A: Make sure everything builds on all platforms
  - Check that the changes section in the manual has all user-visible and packager-visible changes
  - Update the NEWS file (via the manual)
  - ??? make sure documentation is rebuilt correctly (the build process is a little flaky — e.g., sometimes the copy of the manual that’s built into the unison binary is empty when the binary is compiled — make sure “unison -doc topics” looks good)
  - If this is the first time through the loop, update the minor version number from e.g. X.Y.(Z-1).80 to X.Y.Z
  - Tag vX_Y_Z_rcN on GitHub, for N starting at 1
  - Announce on unison-users
  - Evaluate reports and perhaps make changes.
  - If any changes, goto A
  - If no changes, tag the release vZ_Y_Z
  - Announce on unison-users
  - Change the version number to X.Y.Z.80

## breaking changes

Breaking changes in the protocol or storage format are a huge deal for users, requiring them to have the same version everywhere, which is very awkward if they are using different packaging systems on different operating systems.

Therefore, breaking changes should happen only intentionally, with due thought and discussion.

If there is a wire protocol break, the minor version (e.g. 2.52) should be bumped.   Micro versions imply no protocol or storage breaks.