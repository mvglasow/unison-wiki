**Please do not create an issue or ask for help in other channels until you have read carefully this entire wiki page.**

**If you created an issue and it was closed with only a link to this page, please read this page carefully, because the person who closed your issue almost certainly believes that your issue does not follow the rules described here.**

Unison does have a history of being helpful to people who take the time to ask for help in the right channels and follow the guidance in this page.   However, there are a only small number of people doing so, and the guidelines here are meant to maintain that willingness.

# Understand the nature of the Unison project

## Unison's product is the source code

Unison's product is the source code.  This means that problems that are not in the source code release are not Unison bugs.

A packaging system having an old version is not a bug in Unison.  A packaging system having an incorrect build procedure is not a bug in Unison.  Packaging system issues should be reported to the packaging system, and may not be entered in Unison's tracker.

The CI-provided binaries exist for Continuous Integration and are useful for users as a side benefit. Therefore, the CI binaries not working on a particular operating system is not a Unison bug (there might be Unison bug lurking behind that, but there might not). In general, binaries should be provided by packaging systems.

## Unison is only concerned with the most recent release and the tip of git

Generally, problems are fixed on the git master branch, and from time to time a new release is made.  From the project's viewpoint, old releases are obsolete, and bugs in them are no longer relevant.  While the license gives you the right to run old code, no one is interested in helping with that -- advice is essentially always to upgrade.

If you are running an old version of Unison because you choose to run an LTS release, because someone else controls the computer on which it is running, or because your packaging system or operating system has an old version, that is something to be addressed with those parties, not with the Unison project.

## Understand the purpose of the github issue tracker

The issue tracker is for bug reports and (limited) enhancement requests. Specifically, this means that questions and requests for help are not appropriate as issues; those should be directed to unison-users (or unison-hackers if the discussion requires reading the source code).  Questions in the issue tracker will be summarily closed without answers.

# Upgrade to a supported version.

The unison project does not provide support for old versions.  As of 2022-04, only 2.52.0 and newer are considered new enough to be allowed in the issue tracker.  You must upgrade both the local and the remote computer.   (We realize you might not have administrative permissions on the remote, but that does not create an obligation for the unison project to spend time dealing with old versions.)  If you are running an older version, **especially 2.48**, please upgrade before asking for help.  See https://github.com/bcpierce00/unison/wiki/Downloading-Unison for how to get pre-compiled binaries for a limited set of platforms.  The `unison-users` list is the appropriate place for help upgrading.

This guidance to update applies even if your operating system provides an older version.  The group of people contributing to unison maintenance is not responsible for how packaging systems (including GNU/Linux distributions) update unison, even though some of them help with some systems.   Please address issues such as "FooOS 42 has unison 2.48" to FooOS.

# Try to debug the problem yourself

## Look at the Unison documentation

First, look in the [manual](https://github.com/bcpierce00/unison/tree/documentation), and the FAQ section of the old website at https://alliance.seas.upenn.edu/~bcpierce/wiki/index.php.  Lots of questions are answered there.

## Turn on debugging

Next, try running Unison with the "-debug all" command line option. This will cause Unison to generate a detailed trace of what it's doing, which may help pinpoint where the problem is occurring.

## Simplify your setup

Reduce the complexity of what you are doing, even if what you ultimately want is complicated.   Simplification steps include:
  - Sync locally.
  - Use the Text User Interface.
  - Turn off the watcher.
  - Turn off -repeat.
  - Turn off -auto.

If you can succeed at that, add things back one at a time.  If the problem remains, you have created a smaller test case.

Try to create a test case with the smallest number of files that triggers the bug.

## Search existing issues

There may be a bug report already that is similar.  It might contain a workaround.   You might be able to provide additional details, such as if you find a way to avoid or trigger the bug.   See [the github bugtracker](https://github.com/bcpierce00/unison/issues)

## Prepare the required information for the mailinglist or the issue tracker

Please include the version of Unison you are using (`unison -version)`, the ocaml version you compiled with, the OS type you are running it on, the version of the OS, the CPU type, a record of what gets printed when the ``-debug all`` option is included, and as much information as you can about what went wrong.  Be sure to include version information for both machines if syncing non-locally.

# Asking for help and the issue tracker

If after following the steps above, you are still having a problem, you can ask for help on the mailinglist.  If you can articulate that Unison is behaving incorrectly, you can file a bug in the issue tracker.   And, if you find that Unison is meeting its specification, but that different behavior would be useful to you -- and likely to others -- you can file an enhancement request.

## Ask for help on the mailinglist

If the previous steps didn't clarify matters, try sending an email describing your problem to the [users' list](https://github.com/bcpierce00/unison/wiki/Mailing-Lists). (Make sure you subscribe first, so that you'll see people's responses in case they reply only to the list!)

Unlike the issue tracker, mailinglist help requests could be for older versions, but you should still upgrade, because some people have no interest in debugging old versions.

## Reporting a bug

The Github issue tracker has open tickets for bugs, and for enhancement requests.   If you can clearly articulate that the current version of unison is behaving incorrectly, you are welcome to file a bug report.  Bug reports must include the version information described in the previous section.

Note that bugs must be against a recent version, often the most recent version.  Even if you report a bug against 2.51.5 in 2022-04, you will be asked to update and retest.

The language should be along the lines of "unison does this wrong.  I did X and should have gotten Y but Z happened".  If you are about to write "I don't understand how to do X" or "If I did Y would it work", that is a clue that your message belongs on the users list and is not a bug report.   The bug tracker is not a forum, and questions in the bug tracker will be summarily closed.  The bug tracker is also not a consulting service.

Log data must be provided as undamaged text (specifically without incorrect line wrapping) not an image of text.  This is for accessibility, and to enable those reading to choose font size and to be able to search.  Images of the GUI are acceptable when the bug concerns how the GUI displays things.

Your issue, if not closed, will probably get labels with the maintainer's assessment of importance, difficulty, etc.  Do not worry about these decisions; bugs get fixed when someone submits a quality PR, and there is no team working on your high-priority bug.

## Feature requests

Please understand that there are not a lot of people spending a lot of time maintaining unison, and that therefore requests for non-trivial features that would be useful to a tiny number of people are not necessarily a good tradeoff of the usefulness of the request vs the cognitive load of open tickets.  Therefore, such speculative feature tickets may be closed.   That said, well-articulated feature requests that are likely of interest to at least some others are welcome.

Please phrase feature requests as "Add ability to do X" or something along those lines.  Explain precisely what the new behavior is.  Discuss alternative approaches and why the proposed behavior is correct.   If you are unclear on what is desired, pick one of the mailinglists to discuss and crystallize first.