Students
========

This directory contains scripts for testing your machine to make sure
you have the software you'll need for this course.  See
the comments at the head of each script for more details, but you'll
basically want to see something like:

    $ python tuit-installation-test-1.py
    Passed
    $ python tuit-installation-test-2.py
    check virtual-shell...  pass
    …
    Successes:

    virtual-shell Bourne Again Shell (bash) 4.2.37
    …

If you see something like:

    $ python tuit-installation-test-2.py
    check virtual-shell...  fail
    …
    check for command line shell (virtual-shell) failed:
      command line shell (virtual-shell) requires at least one of the following dependencies
      For instructions on installing an up-to-date version, see
      http://software-carpentry.org/setup/
      causes:
      check for Bourne Again Shell (bash) failed:
        could not find 'bash' executable for Bourne Again Shell (bash)
        For instructions on installing an up-to-date version, see
        http://software-carpentry.org/setup/
    …

follow the suggestions to try and install any missing software.  For
additional troubleshooting information, you can use the `--verbose`
option:

    $ python tuit-installation-test-2.py --verbose
    check virtual-shell...  fail
    …
    ==================
    System information
    ==================
    os.name            : posix
    …

Instructors
===========

`tuit-installation-test-1.py` is pretty simple, and just checks that
the students have a recent enough version of Python installed that
they'll be able to parse `tuit-installation-test-2.py`.  The latter
checks for a list of dependencies and prints error messages if a
package is not installed, or if the installed version is not current
enough.  By default, the script checks for pretty much anything that
has ever been used at a Software Carpentry boot camp, which is
probably not what you want for your particular boot camp.

Before your boot camp, you should go through
`tuit-installation-test-2.py` and comment any dependencies you don't
need out of the `CHECKS` list.  You might also want to skim through
the minimum version numbers listed where particular dependencies are
defined (e.g. `('git', 'Git', (1, 7, 0), None)`).  For the most part,
fairly conservative values have been selected, so students with modern
machines should be fine.  If your boot camp has stricter version
requirements, feel free to bump them accordingly.

Similarly, the virtual dependencies can be satisfied by any of several
packages.  If you don't want to support a particular package (e.g. if
you have no Emacs experience and don't want to be responsible for
students who show up with Emacs as their only editor), you can comment
out that particular `or_dependency`.

Finally, don't forget to post your modified scripts somewhere where
your students can download them!
