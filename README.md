buildscript
===========

Script to automate build OpenBSD from source.  Under testing.  Please don't use
this (yet) without expecting some bugs.  Feel free to submit a Pull Request if
you find one, though.

Assumptions:
1. There is a user named cvsync who updates `/home/cvsync/cvs`.  Please see the
included `cvsync.conf`.
2. The version to build is the same as $(uname -r), or VERSION has been set.
3. The architecture to build is the same as `$(uname -m)`.
4. This script is being run as root.

All output from this script will be sent to `/var/log/build.log`.  Running it
like
```ksh
$ sudo ./build & tail -f /var/log/build.log
```
or
```ksh
# ./build &
$ tail -f /var/log/build.log
```
is a good way to get output.

The `pasture/` directory has the previous (and much nicer-looking) incarnation
of this script.  I ended up totally rewriting it.
