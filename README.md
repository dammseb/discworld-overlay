# discworld-overlay
This repository is a playground for various ebuilds I'm authoring (or modifying), mostly for VoIP-related stuff.

### DISCLAIMER
This is work in progress and definitely **NOT** production-quality. Do not use it for anything other than experimentation.
It is provided as-is without warranty of any kind, including fitness for a particular purpose or merchantability.

In addition, download and/or use of ebuilds provided by this repository might result in accessing of code or software for which additional restrictions, imposed by third parties, apply. These might include, but are not limited to, restrictions on distribution and use, or restrictions on producing derivative work. The author of this repository **bears no responsibility against any party** for direct or indirect damages arising from the failure of the user of this repository to comply with such restrictions. By obtaining or using content provided by this repository **you understand and accept** that compliance with licensing and (patent or other) law in your jurisdiction **is solely your own responsibility**, and that access to or acquisition of such code or software **is the result of your actions alone**, as no such code or software is included in this repository.

These disclaimers apply in addition to the terms of the licence under which this work is published. Please see
the LICENSE file for more information.

### Installation
 - This repository is now on layman. To install it, run as root:
```bash
layman -f && layman -a discworld
```
 - Alternatively:
   - Clone the repository:
   ```bash
   cd /usr/local/portage
   git clone https://github.com/gedia/discworld-overlay.git
   ```
   - and add the following to your portage repository configuration (e.g., /etc/portage/repos.conf/local.conf),
     adjusting as necessary:
   ~~~~
   [discworld]
   priority = 99
   sync-type = git
   sync-uri = https://github.com/gedia/discworld-overlay.git
   location = /usr/local/portage/discworld-overlay
   masters = gentoo
   auto-sync = Yes
   ~~~~

### Noteworthy ebuilds
This is a possibly incomplete list of ebuilds included in this Gentoo repository:
 - net-misc/kamailio: A well-known SIP-proxy. You might want to check rion-overlay for alternatives.
 - net-misc/asterisk: A little-tested asterisk 14 ebuild with support for Digium's binary codecs.
   Stable ebuilds are in portage.
 - net-analyzer/homer: A scalable SIP Capture system. I am not aware of other ebuilds for this software.
 - net-proxy/rtpengine: A proxy for RTP traffic and other UDP based media traffic.
   I am not aware of other ebuilds for this software.
 - media-libs/asterisk-g72x: g729 codec module for asterisk, based on either Intel IPP speech codec samples
   or Belledonne Communications' bcg729 code. The ebuild applies a patch to build against Intel IPP libraries dynamically.
   This means that Intel IPP libraries must be in the LDPATH of the machine where the code will be executed.
   This repository provides ebuilds for these libraries as well, and manages the dependency.
 - app-admin/netbox: NetBox is an open source web application designed to help manage and document computer networks.
   Depends on several ebuilds available via the last-hope overlay (https://github.com/ercpe/lh-overlay). You might also need
   to bump versions of some dev-python ebuilds in your local overlay (only filename renaming is necessary and running
   "ebuild /path/to/bumped/verion.ebuild digest". I am not aware of any other ebuilds for this software.
