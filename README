# IMAP Backup Tool

* [mleonhard/imapbackup](https://github.com/mleonhard/imapbackup)
* [tamale.net/imapbackup](http://www.tamale.net/imapbackup/)

This program incrementally backs up IMAP folders to local mbox files.
New messages are appended to the folder's mbox file.


## Features

* Downloads all IMAP folders
* Stores messages in mbox, mbox.gz, or mbox.bz2
* Each folder downloads to its own mbox file, eg. Inbox.Drafts.mbox
* Downloads only new messages, appends them to the mbox file
* IMAP4 SSL, supporting client and server certificates
* Accesses IMAP account in read-only mode. Does not affect message 'seen' status.


## Usage

    Usage: imapbackup [OPTIONS] -s HOST -u USERNAME [-p PASSWORD]
     -a --append-to-mboxes     Append new messages to mbox files. (default)
     -y --yes-overwrite-mboxes Overwite existing mbox files instead of appending.
     -n --compress=none        Use one plain mbox file for each folder. (default)
     -z --compress=gzip        Use mbox.gz files.  Appending may be very slow.
     -b --compress=bzip2       Use mbox.bz2 files. Appending not supported: use -y.
     -f --=folder              Specifify which folders use.  Comma separated list.
     -e --ssl                  Use SSL.  Port defaults to 993.
     -k KEY --key=KEY          PEM private key file for SSL.  Specify cert, too.
     -c CERT --cert=CERT       PEM certificate chain for SSL.  Specify key, too.
                               Python's SSL module doesn't check the cert chain.
     -s HOST --server=HOST     Address of server, port optional, eg. mail.com:143
     -u USER --user=USER       Username to log into server
     -p PASS --pass=PASS       Prompts for password if not specified.

    NOTE: mbox files are created in the current working directory.


## Example

$ python imapbackup.py -s shevek.tamale.net -u michael -e -f INBOX
Password:
Connecting to 'shevek.tamale.net' TCP port 993, SSL
Logging in as 'michael'
Finding Folders: 67 folders
Folder INBOX: 1231 messages
File INBOX.mbox /
WARNING: Message #117 in INBOX.mbox has a malformed Message-Id header.
File INBOX.mbox -
WARNING: Message #269 in INBOX.mbox has a malformed Message-Id header.
File INBOX.mbox -
WARNING: Message #498 in INBOX.mbox has a malformed Message-Id header.
File INBOX.mbox /
WARNING: Message #609 in INBOX.mbox has a malformed Message-Id header.
File INBOX.mbox |
WARNING: Message #976 in INBOX.mbox has a malformed Message-Id header.
File INBOX.mbox -
WARNING: Message #1042 in INBOX.mbox has a malformed Message-Id header.
File INBOX.mbox: 1230 messages
Downloading 1 new messages to INBOX.mbox: 1.89 KB total, 1.89 KB for largest message
Disconnecting
$


## Changelog


- **2009-12-12 v1.4c**
  * Use hashlib module instead of deprecated sha module - Ronan Sheth
  * Added --folders argument - Giuseppe Scrivano
  * imapbackup disappeared from Rui Carmo's site.  This version found at: https://gist.github.com/raw/273418/fe7c59f69ba57c40dde8c8c33d6105f46f458df8/imapbackup.py
- **2008-12-08 v1.4b**
  * Fetch with BODY.PEEK instead of BODY, to avoid marking Gmail messages as read - Brandon Long (Gmail team)
- **2007-05-28 v1.4a**
  * SSL support! Can use a private key file and server certificate chain file. Unfortunately, Python's ssl module doesn't check the certificate chain. This needs to be fixed.
  * You can now specify the port number as part of the server name. Example: `imapbackup.py -u user -s mail.com:1234`
  * Cleaned up code. Used pylint to find code that didn't comply with best practices.
- **2007-05-27 v1.3b**
  * Fixed bug in error message printout.
- **2007-05-26 v1.3a
  * Better support for result of LIST command. Fixes the problem of some folders not getting backed up from Courier IMAPd
  * Improved usage printout, made parameters more consistent.
  * Added support for socket._fileobject.recv bugfix on Windows
- **2007-03-27 v1.2e
  * By Rui Carmo.  Downloaded from:
    http://the.taoofmac.com/space/Projects/imapbackup
    http://web.archive.org/web/20071011040436/http://the.taoofmac.com/space/Projects/imapbackup


## License: BSD

Copyright (C) 2007, Rui Carmo, Michael Leonhard. All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
* Neither the name of the <ORGANIZATION> nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
