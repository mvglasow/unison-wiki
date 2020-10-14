# release process

## rough outline
  - make sure everything builds on all platforms
  - update the minor version number
  - compile a list of changes
  - Update the NEWS file (via the manual) with user-visible and packager-visible changes
  - tag a release version on GitHub
  - announce on unison-users and unison-announce
  - make sure documentation is rebuilt correctly (the build process is a little flaky — e.g., sometimes the copy of the manual that’s built into the unison binary is empty when the binary is compiled — make sure “unison -doc topics” looks good)

## breaking changes

Breaking changes in the protocol or storage format are a huge deal for users, requiring them to have the same version everywhere, which is very awkward if they are using different packaging systems on different operating systems.

Therefore, breaking changes should happen only intentionally, with due thought and discussion.

If there is a wire protocol break, the minor version (e.g. 2.52) should be bumped.   Micro versions imply no protocol or storage breaks.