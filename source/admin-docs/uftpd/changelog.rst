.. _uftpd-changelog:

|logbook-img| Changelog
=======================

.. |logbook-img| image:: ../../_static/logbook.png
  	:height: 22px
  	:align: middle

The UFTP issue tracker is at
https://sourceforge.net/p/unicore/uftp-issues.

UFTPD 3.1.2 (released Dec 16, 2021)
-----------------------------------
 - improvement: support credential as separate key and
   certificate files specified by the 'credential.key' and
   'credential.certificate' properties
 - fix: reply for checksum of files with length zero gave "-1"
   as the last byte

UFTPD 3.1.1 (released Dec 8, 2021)
-----------------------------------
 - new feature: HASH command to get file checksums (#70)
 - fix: cleanup child processes forked in get_user_info()

UFTPD 3.1.0 (released Oct 27, 2021)
------------------------------------
 - improvement: allow to run as unprivileged user with added
   setuid/setgid capabilities via 'setpriv' or similar tool
 - fix: getting a file that exists but is not readable does
   not result in the right error message (#68)
 - fix: STOR without previous RANG command should truncate 
   the file before writing
 - fix: in a "restricted" session, check access permission using
   absolute paths of files

UFTPD 3.0.4 (released Sept 13, 2021)
------------------------------------
 - fix: ACL parsing for DNs with '/' (#66)
 - fix: UFTPD fails when user's home does not exist

UFTPD 3.0.3 (released July 2, 2021)
-----------------------------------
 - fix: writing file chunks was buggy
 
UFTPD 3.0.2 (released May 27, 2021)
-----------------------------------
 - fix: read user keys after privilege drop to avoid
   issues with root-squash filesystems
 - fix: implement rename (RNFR, RNTO)
 - fix: implement append (APPE) and writing to an
   existing file with offset

UFTPD 3.0.1 (released May 10, 2021)
-----------------------------------
 - fix: accept and ignore empty lines on command channel
 - fix: implement MLSD command
 - fix: close existing / "forgotten" data connection when
   client opens a new one
 - fix: date format in MLST and MLSD replies

UFTPD 3.0.0 (released Apr 27, 2021)
-----------------------------------
 - first release of the Python implementation
 - simpler execution model based on fork, every FTP session 
   runs as a separate process
 - cleaner security (users/groups) and better control 
   over file permissions
 - logs to syslog

.. note:
 **KNOWN ISSUES:**
 - removed SYNC command (for now)
 - uploading using both multiple TCP streams and compression is
   not working correctly
