# release process

## rough outline
  - make sure everything builds on all platforms
  - update the minor version number
  - compile a list of changes
  - Update the NEWS file with user-visible and packager-visible changes
  - tag a release version on GitHub
  - optionally, compile binaries on one or more architectures and add them to GitHub
  - announce on unison-users and unison-announce
  - make sure documentation is rebuilt correctly (the build process is a little flaky — e.g., sometimes the copy of the manual that’s built into the unison binary is empty when the binary is compiled — make sure “unison -doc topics” looks good)
  - either put new binaries on download page in Unison web site or else just make that page point to GitHub