# Reporting bugs

If Unison is not working the way you expect, here are some steps to follow.

## Upgrade to a supported version.

The unison project does not provide support for old versions.  As of 2020-10, help will only be provided for 2.51.2 and newer, with a strong preference for 2.51.3 or git master.  If you are running 2.48 or older, please upgrade before asking for help.  See https://github.com/bcpierce00/unison/wiki/Downloading-Unison for how to get precompiled binaries.

This guidance to update applies even if your operating system provides an older version.  The group of people contributing to unison maintenance is not responsible for how packaging systems (including GNU/Linux distributions) update unison, even though some of them help with some systems.   Please address issues such as "FooOS 42 has unison 2.48" to FooOS.

## Look at the Unison documentation

First, look in the manual, and the FAQ section of the old website at https://alliance.seas.upenn.edu/~bcpierce/wiki/index.php.  Lots of questions are answered there.

## Turn on debugging

Next, try running Unison with the "-debug all" command line option. This will cause Unison to generate a detailed trace of what it's doing, which may help pinpoint where the problem is occurring.

## Simplify your setup

Try to reduce the complexity of what you are doing; sync locally even if that's not what you ultimately want.  If you can succeed at that, add things back one at a time.

## Ask for help

If the previous two steps didn't clarify matters, try sending an email describing your problem to the [users' list](https://github.com/bcpierce00/unison/wiki/Mailing-Lists). (Make sure you subscribe first, so that you'll see people's responses in case they reply only to the list!)

Please include the version of Unison you are using (``unison -version)`, the ocaml version you compiled with, the OS type you are running it on, the version of the OS, a record of what gets printed when the ``-debug all`` option is included, and as much information as you can about what went wrong.  Be sure to include version information for both machines.

## Reporting a bug

The Github issue tracker has open tickets for bugs, and for enhancement requests.   If you can clearly articulate that unison is behaving incorrectly, you are welcome to file a bug report.  The language should be along the lines of "unison does this wrong.  I did X and should have gotten Y but Z happened".  If you are about to write "I don't understand how to do X" or "If I did Y would it work", that is a clue that your message belongs on the users list and is not a bug report.