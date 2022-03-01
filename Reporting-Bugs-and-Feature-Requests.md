**Please do not create an issue or ask for help in other channels until you have read carefully this entire wiki page.**

**If you created an issue and it was closed with only a link to this page, please read this page carefully, because the person who closed your issue almost certainly believes that your issue does not follow the rules described here.**

If Unison is not working the way you expect, here are steps to follow.

# Understand the purpose of the github issue tracker

The issue tracker is for bug reports and (limited) enhancement requests. Specifically, this means that questions and requests for help are not appropriate as issues; those should be directed to unison-users (or unison-hackers if the discussion requires reading the source code).  Questions in the issue tracker will be summarily closed without answers.

# Upgrade to a supported version.

The unison project does not provide support for old versions.  As of 2022-02, only 2.51.5 and newer are considered new enough to be allowed in the issue tracker.  If you are running an older version, **especially 2.48**, please upgrade before asking for help.  See https://github.com/bcpierce00/unison/wiki/Downloading-Unison for how to get precompiled binaries for a limited set of platforms.

This guidance to update applies even if your operating system provides an older version.  The group of people contributing to unison maintenance is not responsible for how packaging systems (including GNU/Linux distributions) update unison, even though some of them help with some systems.   Please address issues such as "FooOS 42 has unison 2.48" to FooOS.

# Look at the Unison documentation

First, look in the manual, and the FAQ section of the old website at https://alliance.seas.upenn.edu/~bcpierce/wiki/index.php.  Lots of questions are answered there.

## Turn on debugging

Next, try running Unison with the "-debug all" command line option. This will cause Unison to generate a detailed trace of what it's doing, which may help pinpoint where the problem is occurring.

## Simplify your setup

Try to reduce the complexity of what you are doing.  Sync locally even if that's not what you ultimately want.  Turn off the watcher.  If you can succeed at that, add things back one at a time.

## Search existing issues

There may be a bug report already that is similar.  It might contain a workaround.   You might be able to provide additional details, such as if you find a way to avoid or trigger the bug.   See https://github.com/bcpierce00/unison/issues

## Ask for help

If the previous steps didn't clarify matters, try sending an email describing your problem to the [users' list](https://github.com/bcpierce00/unison/wiki/Mailing-Lists). (Make sure you subscribe first, so that you'll see people's responses in case they reply only to the list!)

Please include the version of Unison you are using (``unison -version)`, the ocaml version you compiled with, the OS type you are running it on, the version of the OS, the CPU type, a record of what gets printed when the ``-debug all`` option is included, and as much information as you can about what went wrong.  Be sure to include version information for both machines if syncing non-locally.

## Reporting a bug

The Github issue tracker has open tickets for bugs, and for enhancement requests.   If you can clearly articulate that the current version of unison is behaving incorrectly, you are welcome to file a bug report.  Bug reports must include the version information described in the previous section.

Note that bugs must be against a recent version, often the most recent version.  Even if you report a bug against 2.51.4 in 2022-02, you will likely be asked to update and retest.

The language should be along the lines of "unison does this wrong.  I did X and should have gotten Y but Z happened".  If you are about to write "I don't understand how to do X" or "If I did Y would it work", that is a clue that your message belongs on the users list and is not a bug report.   The bug tracker is not a forum, and questions in the bug tracker will be summarily closed.

Please set labels, and do not be offended if they are summarily adjusted.  Typically, defect or crash is appropriate.

## Feature requests

Please understand that there are not a lot of people spending a lot of time maintaining unison, and that therefore requests for non-trivial features that would be useful to a tiny number of people are not necessarily a good tradeoff of the usefulness of the request vs the cognitive load of open tickets.  Therefore, such speculative feature tickets may be closed.   That said, feature requests that are likely of interest to at least some others are welcome.

Please phrase feature requests as "Add ability to do X" or something along those lines.