# Old bugs

Wholesale import of src/TODO.txt, with pruning of things believed
fixed or listed in the tracker.

# SERIOUS

```
[APril 2002, Jason Eisner] Recently I found an aliasing problem that may
  endanger Unison's semantics.
  --
  The problem is with the "follow" directive, which is documented like
  this: "Including the preference -follow <pathspec> causes Unison to
  treat symbolic links matching <pathspec> as 'invisible' and behave as
  if the thing pointed to by the link had appeared literally at this
  place in the replica."
  --
  If one of these invisible (elsewhere called "transparent") symlinks
  points outside the replica, all is well and good.  But if it points to
  something in the replica, then Unison now has two names for the same
  file.  It doesn't currently detect the aliasing.  As a result, it keeps
  separate information for the two names in the archive files.
  [A long example is in a mailmessage in BCP's files]
```

# MINOR

```
BCP  [May 2002]
  The "rescan paths that failed previous sync" function misses some files.
  E.g., if a directory has failed to transfer because the disk ran out of
  space and I hit 'f', it will come back with "Everything is up to date",
  even though doing a full re-sync will again recognize the directory as
  needing to be transferred.

Jason Eisner [April, 2002]
  The Merge feature does not appear to modify file times.  Thus, when
  times=true, using the Merge feature on
     changed ? changed    myfile
  turns it into
     props   ? props      myfile
  and to finish the sync, I have to decide which file time "wins."
  This differs from the behavior that I would expect and find more
  convenient: namely, if I perform the merge at 3pm, then it counts as a
  change to BOTH replicas of myfile and they should both end up with a
  time of 3pm.
  So I'd suggest that myfile in the local replica should have its
  modtime as well as its contents changed to that of
  #unisonmerged-myfile (the temporary file produced by the Merge
  program).  Then this modtime and contents should be propagated to the
  remote myfile as usual, handling clock skew as for any other propagation.
  Other file properties should probably NOT be propagated.

Karl Moerder:
  The synchronization of modification times does not work on directories
  (WinNT folders) or on read-only files. I found this when I tried to
  synchronize mod times on an otherwise synchronized tree. It failed
  gracefully on these. The "[click..." message is a nice touch.
  ==> [Nothing we can do for read-only files; need to patch ocaml for
       directories...]

"After I synchronized two directories I created a new profile, which
  defaulted to the same directories.  I synchronized again (no changes,
  which was fine) but the Unison program did not save the directory names
  in the new profile.  Later attemts to use that new profile failed, of
  course, and further random clicking resulted in a message asking me to
  delete non-existent lock files.  I responded by exiting the program,
  manually deleting the .prf file, and starting over.  This is a minor
  bug, I suppose, the root cause of which is the failure to save the
  directory names in a new profile when they were copied unchanged from a
  previous profile and/or no files had changed in these directories --
  the type of bug that can only affect a new user, and so easy to
  overlook in testing."
```

# COSMETIC

```
Interactively adding an ignore pattern for src will not make
  src/RECENTNEWS immediately disappear (as it does not directly match
  the pattern)...
```
