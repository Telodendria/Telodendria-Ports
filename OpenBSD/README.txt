OpenBSD Porting
===============

This file documents the procedure for updating the OpenBSD port of Telodendria.

Initial Port Submission
-----------------------

This port should be placed at net/telodendria. This README should *not* be
included with the port.

Port directories are mostly self-contained, but the following things outside the
port directory must be updated for the initial port submission:

  1. Consult /usr/ports/infrastructure/db/users.list and make sure to set the
	 right uid and gid in pkg/PLIST based on what's available, as new ports
	 have surely been added since I wrote the PLIST.
  2. Add an entry in net/Makefile

Updating
--------

To update the port to a newer version of Telodendria, follow these steps in the
port directory:

  1. Update the version information in Makefile
  2. make makesum
  3. make fake
  4. make update-plist
  5. make package

If everything works, then a diff of the port directory should be submitted to
the mailing list. Do be sure to look over the diff and make sure everything
looks okay.
