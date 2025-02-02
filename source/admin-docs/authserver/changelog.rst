.. _auth-server-changelog:


|logbook-img| Changelog
=======================

.. |logbook-img| image:: ../../_static/logbook.png
  	:height: 22px
  	:align: middle

The UFTP issue tracker is at
https://sourceforge.net/p/unicore/uftp-issues.

.. note::
 See :ref:`auth-server-update` for how to update.


Auth Server 2.6.0 (released Dec 15, 2021)
------------------------------------------
 - update to UNICORE 8.3 base libs
   includes fix for Log4shell vulnerability

Auth Server 2.5.0-p1 (released Nov 3, 2021)
--------------------------------------------
 - remove unneeded xerces jar from lib directory
   which caused errors on Java 8

Auth Server 2.5.0 (released Oct 27, 2021)
-----------------------------------------
 - update to UNICORE 8.2 base libs
 - updated ssh key handling with support for PuTTy keys
 - fix: upload to share does not work with uftpd 3.x (#69)
 - fix: deleting shares failed if target file no longer
   existed
 - fix: improve replies to uftp 'info' command for users who
   are authenticated but not authorized, and in case
   the uftpd server(s) are down

Auth Server 2.4.0 (released Mar 5, 2021)
-----------------------------------------
 - update to UNICORE 8.1 base libs
 - update to log4j2
 - fix: debian package now depends on "default-jre-headless"

Auth Server 2.3.0 (released Sep 21, 2020)
-----------------------------------------
 - fix: less harsh timeouts when checking connection
   and sending requests to uftpd
 - fix: typo in log4j setup in default conf/startup.properties
 - new feature: support creating "persistent" UFTP sessions
   that allow re-using the login secret multiple times
 - fix: support ECDSA keys
 - update to UNICORE 8.0.4 base libs
 
Auth Server 2.2.1 (released Jul 07, 2020)
-----------------------------------------
 - fix: correctly parse user's access keys (ssh pubkeys)
   as returned by uftpd
 - optimized partial downloads of shared files
   via plain HTTPs

Auth Server 2.2.0 (released Jun 17, 2020)
-----------------------------------------
 - support for more SSH key types (esp. ed25519)

Auth Server 2.1.0 (released Feb 21, 2020)
-----------------------------------------
 - new feature: anonymous (http) download sets the Content-Disposition header
 - new feature: anonymous (http) download has basic support for byte ranges
 - fix: DB table name for storing shares is now 'SHARES_<servername>'
   WARNING if you use data sharing in production, your existing shares
   need to be converted/transferred or they will be lost.
   Please contact us!
 - allow uftp access to anonymous shares via "uftp get-share"
 - improved error responses

Auth Server 2.0.0 (released Jan 20, 2020)
-----------------------------------------
 - update to UNICORE 8.0 base libs
 - simpler, properties-only configuration
 - new feature: multiple UFTPD servers can be configured
   to provide round-robin and/or failover operation (#51)

Auth Server 1.5.0 (released Aug 20, 2019)
-----------------------------------------
 - update to UNICORE 7.13 base libs
 - smarter handling of errors when retrieving SSH keys
 
Auth Server 1.4.0 (released Jul 11, 2018)
-----------------------------------------
 - update to UNICORE 7.10 base libs
 - new feature: data sharing service included in authserver (#33)
 - new feature: SSHKey authentication can use ~/.ssh/authorized_keys (#47)
 - fix: SSHKey authentication does not work when SSHKey is
   the first authenticator in the chain (#37)

Auth Server 1.3.0 (released Nov 29, 2016)
-----------------------------------------
 - update to UNICORE 7.7 base libs
 - provide rmp and deb packages
 - new feature: handle user's groups correctly: pass the
   preferred group to UFTPD and report the available groups via
   the 'info' reply (https://sourceforge.net/p/unicore/uftp-issues/31)

Auth Server 1.2.0 (released June 3, 2016)
-----------------------------------------
 - update to UNICORE 7.6 base libs
 - report UFTPD connection status via REST GET
   operation (i.e. 'uftp info' command)

Auth Server 1.1.1 (released Nov 18, 2014)
-----------------------------------------
 - fix: real client IP from Gateway was not forwarded
   to UFTPD
 - fix: disable SSLv3 ("poodle" vulnerability) 
 - fix: typos in manual and example userdb.txt file

Auth Server 1.1.0 (released Nov 3, 2014)
----------------------------------------
 - new feature: support include/exclude patterns
   (works with UFTPD 2.2.0 and higher)
 - fix: pass on encryption and compression options to
   UFTPD

Auth Server 1.0.0 (released Sept 19, 2014)
------------------------------------------

First release

