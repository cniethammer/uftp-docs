.. _uftp-client-changelog:

|logbook-img| Changelog
=======================

.. |logbook-img| image:: ../../_static/logbook.png
  	:height: 22px
  	:align: middle

Change log for the UFTP standalone client.
The issue tracker is at
https://sourceforge.net/p/unicore/uftp-issues/.

UFTP Client 1.4.4 (released Feb 03, 2022)
-----------------------------------------
 - fix: when running on Windows, remote paths
   erroneously contained '\' characters
 - fix: better error messages in case of missing arguments
 - improvement: for 'rm' command, add '-r' option that
   will also delete (sub-)directories

UFTP Client 1.4.3 (released Dec 15, 2021)
-----------------------------------------
 - update to latest UNICORE base libs
 - new feature: 'checksum' command for getting
   hashes (MD5, SHA-1, SHA-256, SHA-512) for remote
   files from server (requires UFTPD 3.1.1 or later!)
 - fix: 'info' command: handle anonymous user correctly for
   UNICORE Storage endpoints
 - fix: always show https access link for new shares

UFTP Client 1.4.2 (released Aug 19, 2021)
-----------------------------------------
 - improvement: add configurable write buffer size for
   filesystem writes
 - fix: set file modification time (MFMT) used wrong
   time of day
 - fix: Windows: uftp.bat was not working, update docs,
   handle more types of PuTTY keys
 - improvement: try to extract authserver's error message
   in case of auth failure
 - update dependencies

UFTP Client 1.4.1 (released Apr 8, 2021)
----------------------------------------
 - fix: upload in "resume" mode (cp -R) fails when target file
   doesn't exist
 - fix: correctly handle server's multi-stream limit of "1"

UFTP Client 1.4.0 (released Mar 5, 2021)
----------------------------------------
 - new feature: "autheticate" command for only authenticating
   and printing connect info
 - update to log4j2
 - commands can be abbreviated, e.g. "i" for "info"
 - 'cp' command: byte range can now ba simplified to just a single
   number of bytes to transfer, e.g. "uftp cp -B 10G ..."
 - fix: debian package now depends on "default-jre-headless"

UFTP Client 1.3.2 (released Sep 18, 2020)
-----------------------------------------
 - new feature: support FTP proxies (DeleGate, Frox)
 - fix: check ~/.uftp before ~/.ssh for private keys

UFTP Client 1.3.1 (released Jul 21, 2020)
-----------------------------------------
 - fix: don't query password for password-less keys 
 - fix: SSH: make sure key specified by "--identity ..." is used
   when ssh-agent is present

UFTP Client 1.3.0 (released Jun 17, 2020)
-----------------------------------------
 - SSH: support for ed25519 keys
 - SSH: improved ssh-agent support when multiple keys
   are available

UFTP Client 1.2.0 (released Apr 16, 2020)
-----------------------------------------
 - improved error messages and removed stack traces
 - fix: client can hang when multiple threads are
   used (#60)


UFTP Client 1.1.0 (released Feb 13, 2020)
-----------------------------------------
 - improved "share" command
   (thanks to Jens Henrik Goebbert for many suggestions)
   - add separate option for server URL. If not given, the
   server URL is read from environment variable UFTP_SHARE_URL
   - non-absolute paths will be made absolute
   - --anonymous is the default sharing mode
 - console output for new shares now prints the http access URL
   and the full share info in verbose mode
 - if no auth option is given, use "-u $USER" as default
 - renamed 'get'/'put' to 'get-share'/'put-share'
 - fix: truncate existing local file when downloading to avoid
   corrupted file by only partially overwriting existing data (#56)

UFTP Client 1.0.0 (released Sep 30, 2019)
-----------------------------------------
 - new feature: client can create session using a UNICORE/X
   storage URL. This allows to use the client with
   any UNICORE installation that supports UFTP (#55)
 - new feature: 'cp' supports "archive" mode (2.7+ server)
   to unpack tar/zip streams on the server (#53)
 - new feature: support oidc-agent for authentication (#52)
 - new feature: allow to limit bandwidth per FTP connection
   ('-K <limit>', e.g. '-K 100M' limits to 100MB/sec)
 - new feature: deb and rpm packages available
 - ls: nicer output, added '-H' option for more human-readable 
   file size printout
 - fix: client should not try to open files in rw mode for upload
 - fix: error trying to set file mod time on "/dev/..." files
 - fix: local target directories are not created
 - fix: show correct file size for large files
 - fix: 'cp' recursion behaviour should match Unix 'cp'
 - remove non-functional buffer size option

UFTP Client 0.9.1 (released Aug 27, 2019)
-----------------------------------------
 - improved progress output in '-v' mode
 - cleaner handling of UFTPD server rejecting new client
   connections

UFTP Client 0.9.0 (released May 28, 2019)
-----------------------------------------
 - new feature: multiple client threads to
   speed up transfer of many files or large files in
   high-performance networks. Option "-t <n>" selects
   number of threads, "-T <nnn>" determines the minimum
   size of files that will be split up.

UFTP Client 0.8.0 (released Feb 4, 2019)
----------------------------------------
 - update to latest uftp-core and UNICORE base versions
 - new option "-i" to select SSH identity file (#49)

UFTP Client 0.7.0 (released  Jul 19, 2017)
------------------------------------------
 - new feature: data sharing support
   'share', 'get', 'put' commands (#33)

UFTP Client 0.6.0 (released  Nov 25, 2016)
------------------------------------------
 - new feature: 'mkdir' command
 - new feature: 'rm' command
 - fix: accept multiple sources for cp
   (https://sourceforge.net/p/unicore/uftp-issues/23)
 - make 'cp' behave more like Unix 'cp'
 - new feature: 'cp' can preserve file modification times
   (https://sourceforge.net/p/unicore/uftp-issues/28)
 - new feature: '-g' option to pass requested group name
   to auth server (and thus uftpd)
   (https://sourceforge.net/p/unicore/uftp-issues/31)
 - new feature: windows executable 'uftp.bat'
   (https://sourceforge.net/p/unicore/uftp-issues/18)

UFTP Client 0.5.0 (released June 14, 2016)
------------------------------------------
 - new feature: simpler URL scheme without username/password. 
   Username/password given via "-u" option
 - new feature: support for different authorization headers, 
   e.g. OIDC Bearer, via "-A" option
 - fix: better SSH agent support

UFTP Client 0.4.0 (released Jan 26, 2015)
-----------------------------------------

 - new feature: "-r" option in "cp" command 
   attempts to resume a prior transfer
 - new feature: "info" command

UFTP Client 0.3.0 (released Nov 6, 2014)
----------------------------------------

 - fix: agent support
 - fix: handling remote paths
 - new feature: encryption and compression support 
   (requires at least UFTPD 2.2.0 and authserver 1.1.0)

UFTP Client 0.2.0 (released Oct 2, 2014)
----------------------------------------

 - new feature: "cp" can read from / write to console 
   streams, indicated by using "-" as file name
 - improvement: html/pdf manual with more extensive 
   documentation

UFTP Client 0.1.0 (released Sept 19, 2014)
------------------------------------------

First release

