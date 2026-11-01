# linux-assignment

## تکلیف اول

### ۱. نمایش مسیر فعلی

```bash
pwd
```

خروجی:

```
/home/ubuntu
```

### ۲. رفتن به دایرکتوری etc و بررسی مسیر

```bash
cd /etc
pwd
```

خروجی:

```
/etc
```

### ۳. نمایش لیست کامل فایل‌ها (شامل فایل‌های مخفی)

```bash
ls -la
```

بخشی از خروجی:

```
total 404
drwxr-xr-x  1 root                 root                   680 Nov  1 11:00 .
drwxr-xr-x  1 root                 root                   260 Nov  1 10:45 ..
...
```

### ۴. بازگشت به دایرکتوری home

```bash
cd ~
pwd
```

خروجی:

```
/home/ubuntu
```






       -S     Sort by file size, largest first.

       -t     Sort by modification time (the  'mtime'  in  the  inode),  newest
              first.

       -v     Natural sort of (version) numbers in the filenames.

       -X     Sort alphabetically by entry extension.

       -U     Do  not sort; list the files in whatever order they are stored in
              the directory.  This is especially useful when listing very large
              directories, since  not  doing  any  sorting  can  be  noticeably
              faster.

       -L, --dereference
              When  showing file information for a symbolic link, show informa‐
              tion for the file the link references rather than  the  link  it‐
              self.

       --dereference-command-line-symlink-to-dir
              Do  not  follow symlinks except when they link to directories and
              are given as command line arguments.

 Manual page ls(1) line 155/314 59% (press h for help or q to quit)

OPTIONS
       --help Print help information.
 Manual page sort(1) line 1 (press h for help or q to quit)

___________________________________
ubuntu@ubuntu:~$ man ls
ubuntu@ubuntu:~$ cd /etc
ubuntu@ubuntu:/etc$ ls -lS
total 399
-rw-r--r--  1 root                 root                 78419 Oct 14  2025 mime.types
-rw-r--r--  1 root                 root                 70187 Nov  1 10:46 ld.so.cache
-rw-r--r--  1 root                 root                 30761 Mar 20  2026 brltty.conf
-rw-r--r--  1 root                 root                 12990 Mar 15  2025 services
-rw-r--r--  1 root                 root                 12026 Nov 20  2025 nanorc
-rw-r--r--  1 root                 root                 10749 Feb  2  2026 sensors3.conf
-rw-r--r--  1 root                 root                  9804 Mar 13  2026 sudo_logsrvd.conf
-rw-r--r--  1 root                 root                  9636 Aug 26 05:28 locale.gen
-rw-r--r--  1 root                 root                  7649 Aug 26 05:31 pnm2ppa.conf
-rw-r--r--  1 root                 root                  6274 Aug 26 05:28 ca-certificates.conf
-rw-r--r--  1 root                 root                  6174 Aug 26 05:27 ca-certificates.conf.dpkg-old
-rw-r--r--  1 root                 root                  5939 Feb  2  2026 login.defs
-rw-r--r--  1 root                 root                  5513 Sep 13  2025 rygel.conf
-rw-r--r--  1 root                 root                  5230 Feb  2  2026 manpath.config
-rw-r--r--  1 root                 root                  4942 Aug 19 23:59 wgetrc
-rw-r--r--  1 root                 root                  4448 Apr 16  2024 hdparm.conf
-rw-r--r--  1 root                 root                  4354 Mar 13  2026 sudo.conf
-rw-r--r--  1 root                 root                  4027 Nov  4  2025 adduser.conf
-rw-r--r--  1 root                 root                  3986 Mar 15  2026 gprofng.rc
-rw-r--r--  1 root                 root                  3663 Sep 19  2025 screenrc
-rw-r--r--  1 root                 root                  3144 Oct 17  2022 protocols
-rw-r--r--  1 root                 root                  2967 Feb 16  2026 debconf.conf
-rw-r--r--  1 root                 root                  2856 Nov  1 10:46 passwd
-rw-r--r--  1 root                 root                  2786 Nov  1 10:45 passwd-
-rw-r--r--  1 root                 root                  2584 Jan 23  2026 gai.conf
-rw-r--r--  1 root                 root                  2553 Feb 13  2026 bash.bashrc
-rw-r--r--  1 root                 root                  1936 Mar 15  2025 ethertypes
-rw-r--r--  1 root                 root                  1875 Feb 13  2026 inputrc
-r--r-----  1 root                 root                  1800 Jan 21  2026 sudoers
-rw-r--r--  1 root                 root                  1787 Feb  2  2026 request-key.conf
-rw-r--r--  1 root                 root                  1706 Nov  4  2025 deluser.conf
drwxr-xr-x  3 root                 root                  1652 Aug 26 05:33 sane.d
-rw-r--r--  1 root                 root                  1523 Dec  1  2025 usb_modeswitch.conf
-rw-r-----  1 root                 shadow                1309 Nov  1 11:00 shadow
-rw-r--r--  1 root                 root                  1309 Mar 31  2026 paperspecs
-rw-r--r--  1 root                 root                  1289 Jan  6  2026 dhcpcd.conf
-rw-r--r--  1 root                 root                  1274 Nov  1 10:46 group
-rw-r--r--  1 root                 root                  1259 Feb 26  2026 ucf.conf
-rw-r--r--  1 root                 root                  1213 Aug 21  2025 rsyslog.conf
-rw-r-----  1 root                 shadow                1206 Nov  1 10:45 shadow-
-rw-r--r--  1 root                 root                  1152 Nov  1 10:46 group-
-rw-r--r--  1 root                 root                  1136 Nov  5  2025 crontab
drwxr-xr-x  2 root                 root                  1130 Aug 26 05:28 console-setup
-rw-r-----  1 root                 shadow                1099 Nov  1 10:46 gshadow
-rw-r-----  1 root                 shadow                 981 Nov  1 10:46 gshadow-
-rw-r--r--  1 root                 root                   911 Oct 17  2022 rpc
-rw-r--r--  1 root                 root                   775 Feb 13  2026 mke2fs.conf
-rw-r--r--  1 root                 root                   767 Mar 28  2026 netconfig
-rw-r--r--  1 root                 root                   725 Mar 21  2026 fuse.conf
-rw-r--r--  1 root                 root                   711 Aug 26 05:30 hosts.deny
-rw-r--r--  1 root                 root                   685 Feb 13  2026 e2scrub.conf
-rw-r--r--  1 root                 root                   681 Feb 15  2026 xattr.conf
-rw-r--r--  1 root                 root                   641 Apr 20  2026 profile
-rw-r--r--  1 root                 root                   594 Aug 26 05:30 nsswitch.conf
-rw-r--r--  1 root                 root                   586 Dec  6  2025 logrotate.conf
-rw-r--r--  1 root                 root                   552 Jul  3  2025 pam.conf
-rw-r--r--  1 root                 root                   460 Jan 20  2023 zsh_command_not_found
-rw-r--r--  1 root                 root                   437 Nov  1 10:46 casper.conf
-rw-r--r--  1 root                 root                   411 Aug 26 05:30 hosts.allow
-rw-r--r--  1 root                 root                   394 Oct 31  2025 anacrontab
drwxr-xr-x  2 root                 root                   380 Aug 26 05:31 libibverbs.d
-rw-r--r--  1 root                 root                   367 Mar 10  2026 bindresvport.blacklist
drwxr-xr-x  4 root                 root                   311 Aug 26 05:30 security
drwxr-xr-x  2 root                 root                   286 Aug 26 05:33 update-motd.d
-rw-r--r--  1 root                 root                   267 Apr 20  2026 legal
drwxr-xr-x  8 root                 root                   266 Aug 26 05:31 ppp
drwxr-xr-x 11 root                 root                   258 Aug 26 05:33 X11
-rwxr-xr-x  1 root                 root                   243 Jun 10  2025 nftables.conf
-rw-r--r--  1 root                 root                   243 Nov  1 10:45 hosts
drwxr-xr-x  2 root                 root                   240 Aug 26 05:35 grub.d
drwxr-xr-x  2 root                 root                   231 Aug 26 05:33 xml
drwxr-xr-x  3 root                 root                   226 Aug 26 05:31 ufw
-rw-r--r--  1 root                 root                   212 Aug 26 05:27 modules
-rw-r--r--  1 root                 root                   191 Mar 20  2026 libaudit.conf
drwxr-xr-x  1 root                 root                   180 Nov  1 10:46 ssh
drwxr-xr-x  1 root                 root                   165 Aug 26 06:27 rc6.d
drwxr-xr-x  1 root                 root                   165 Aug 26 06:27 rc0.d
drwxr-xr-x  4 root                 root                   156 Aug 26 05:27 chrony
drwxr-xr-x  8 root                 root                   154 Aug 26 05:30 NetworkManager
drwxr-xr-x  1 root                 root                   144 Aug 26 06:27 init.d
drwxr-xr-x  1 root                 root                   142 Aug 26 06:27 alternatives
-rw-r--r--  1 root                 root                   134 Aug 26 05:33 shells
drwxr-xr-x  2 root                 root                   126 Aug 26 05:31 cron.daily
drwxr-xr-x  1 root                 lp                     120 Nov  1 11:01 cups
drwxr-xr-x  8 root                 root                   118 Aug 26 05:27 networkd-dispatcher
drwxr-xr-x  1 root                 root                   117 Aug 26 06:27 rc1.d
drwxr-xr-x  7 root                 root                   117 Aug 26 05:30 brltty
drwxr-xr-x  3 root                 root                   113 Aug 26 05:33 sgml
-rw-r--r--  1 root                 root                   111 Feb  2  2026 magic.mime
-rw-r--r--  1 root                 root                   111 Feb  2  2026 magic
drwxr-xr-x  1 root                 root                   110 Aug 26 06:27 apparmor.d
-rw-r--r--  1 root                 root                   107 Aug 24 10:33 lsb-release
-rw-r--r--  1 root                 root                   106 Aug 26 05:27 environment
drwxr-xr-x  1 root                 root                   104 Aug 26 06:27 rcS.d
-rw-r--r--  1 root                 root                    92 Apr 20  2026 host.conf
-rw-r--r--  1 root                 root                    91 Apr 20  2026 networks
drwxr-xr-x  6 root                 root                    88 Aug 26 05:30 network
drwxr-xr-x  3 root                 root                    86 Aug 26 06:19 libreoffice
drwxr-xr-x  3 root                 root                    85 Aug 26 05:31 update-manager
drwxr-xr-x  2 root                 root                    82 Aug 26 05:31 rsyslog.d
drwxr-x---  1 root                 root                    80 Nov  1 10:46 sudoers.d
drwxr-xr-x  1 root                 root                    80 Aug 26 06:27 systemd
drwxr-xr-x  1 root                 root                    80 Aug 26 05:28 ssl
drwxr-xr-x  2 root                 root                    76 Aug 26 05:27 newt
drwxr-xr-x  1 root                 root                    76 Aug 26 06:27 rc5.d
drwxr-xr-x  1 root                 root                    76 Aug 26 06:27 rc4.d
drwxr-xr-x  1 root                 root                    76 Aug 26 06:27 rc3.d
drwxr-xr-x  1 root                 root                    76 Aug 26 06:27 rc2.d
drwxr-xr-x  5 root                 root                    76 Aug 26 05:30 ModemManager
drwxr-xr-x  5 root                 root                    76 Aug 26 05:29 vulkan
drwxr-xr-x  1 root                 root                    76 Aug 26 06:27 default
drwxr-xr-x  2 root                 root                    75 Aug 26 05:31 wpa_supplicant
drwxr-xr-x  2 root                 root                    70 Aug 26 05:31 bluetooth
drwxr-xr-x  3 root                 root                    69 Aug 26 05:31 avahi
drwxr-xr-x  4 root                 root                    69 Aug 26 05:31 openvpn
drwxr-xr-x  2 root                 root                    69 Aug 26 05:31 udisks2
drwxr-xr-x  3 root                 root                    67 Aug 26 06:27 lvm
drwxr-xr-x  2 root                 root                    66 Aug 26 05:27 skel
drwxr-xr-x  2 root                 root                    65 Aug 26 05:31 cron.weekly
drwxr-xr-x  5 root                 root                    65 Aug 26 05:29 apm
drwxr-xr-x  4 root                 root                    65 Aug 26 05:31 speech-dispatcher
drwxr-xr-x  4 root                 root                    64 Aug 26 05:27 dpkg
drwxr-xr-x  4 root                 root                    64 Aug 26 06:27 zfs
drwxr-xr-x  2 root                 root                    63 Aug 26 05:33 environment.d
drwxr-xr-x  2 root                 root                    63 Aug 26 05:27 supercat
drwxr-xr-x  2 root                 root                    62 Aug 26 06:27 request-key.d
drwxr-xr-x  2 root                 root                    61 Aug 26 05:33 gtk-3.0
drwxr-xr-x  2 root                 root                    61 Aug 26 05:28 ld.so.conf.d
drwxr-xr-x  2 root                 root                    60 Aug 26 05:31 modules-load.d
drwxr-xr-x  3 root                 root                    60 Aug 26 05:30 tpm2-tss
drwxr-xr-x  1 root                 root                    60 Nov  1 10:46 netplan
drwxr-xr-x  1 root                 root                    60 Nov  1 10:45 gdm3
drwxr-xr-x  1 root                 root                    60 Aug 26 05:29 xdg
drwxr-xr-x  1 root                 root                    60 Aug 26 05:44 apt
drwxr-xr-x  1 root                 root                    60 Aug 26 05:29 polkit-1
drwxr-xr-x  1 root                 root                    60 Aug 26 05:31 fwupd
drwxr-xr-x  1 root                 root                    60 Nov  1 10:45 pam.d
-rw-r--r--  1 root                 root                    59 Nov  1 10:45 fstab
drwxr-xr-x  1 root                 root                    58 Aug 26 06:27 logcheck
drwxr-xr-x  1 root                 root                    58 Aug 26 06:27 initramfs-tools
drwxr-xr-x  4 root                 root                    57 Aug 26 06:19 lighttpd
drwxr-xr-x  2 root                 root                    57 Aug 26 05:33 PackageKit
drwxr-xr-x  3 root                 root                    56 Aug 26 05:31 apport
drwxr-xr-x  3 root                 root                    55 Aug 26 05:31 UPower
drwxr-xr-x  3 root                 root                    55 Aug 26 05:31 pulse
drwxr-s---  2 root                 dip                     54 Aug 26 05:31 chatscripts
-rw-r--r--  1 root                 root                    54 Aug 26 05:56 crypttab
drwxr-xr-x  2 root                 root                    54 Aug 26 05:30 bash_completion.d
drwxr-xr-x  2 root                 root                    52 Aug 26 05:30 sysstat
drwxr-xr-x  1 root                 root                    51 Aug 26 06:27 cloud
drwxr-xr-x  2 root                 root                    51 Aug 26 05:30 cron.monthly
drwxr-xr-x  2 root                 root                    51 Aug 26 05:30 cron.yearly
drwxr-xr-x  4 root                 root                    50 Aug 26 05:29 pki
drwxr-xr-x  2 root                 root                    50 Aug 26 05:33 dictionaries-common
drwxr-xr-x  2 root                 root                    50 Aug 26 05:31 groff
drwxr-xr-x  2 root                 root                    49 Aug 26 05:31 thermald
drwxr-xr-x  3 root                 root                    49 Aug 26 05:33 geoclue
drwxr-xr-x  4 root                 root                    49 Aug 26 05:29 ghostscript
drwxr-xr-x  1 root                 root                    49 Aug 26 05:30 kernel
drwxr-xr-x  4 root                 root                    48 Aug 26 05:27 dbus-1
drwxr-xr-x  3 root                 root                    47 Aug 26 05:31 gdb
drwxr-xr-x  2 root                 root                    46 Aug 26 05:28 vim
drwxr-xr-x  1 root                 root                    46 Aug 26 06:27 profile.d
-rw-r--r--  1 root                 root                    45 Sep 28  2025 bash_completion
drwxr-xr-x  3 root                 root                    44 Aug 26 05:27 dhcp
drwxr-xr-x  2 root                 root                    44 Aug 26 05:30 libnl-3
-rw-r--r--  1 root                 root                    43 Nov  1 10:46 subuid
-rw-r--r--  1 root                 root                    43 Nov  1 10:46 subgid
drwxr-xr-x  2 root                 root                    43 Aug 26 05:31 cupshelpers
drwxr-xr-x  2 root                 root                    43 Aug 26 05:31 krb5.conf.d
drwxr-xr-x  2 root                 root                    42 Aug 26 05:30 tmpfiles.d
drwxr-xr-x  4 root                 root                    40 Aug 26 05:30 dconf
drwxr-xr-x  2 colord               colord                  40 Nov  1 11:00 colord
lrwxrwxrwx  1 root                 root                    39 Aug 26 05:27 resolv.conf -> ../run/systemd/resolve/stub-resolv.conf
drwxr-xr-x  2 root                 root                    39 Aug 26 05:28 python3.14
drwxr-xr-x  1 root                 root                    39 Aug 26 06:27 sysctl.d
drwxr-xr-x  2 root                 root                    38 Aug 26 05:30 gnome
drwxr-xr-x  2 root                 root                    37 Aug 26 05:31 plymouth
drwxr-xr-x  3 root                 root                    37 Aug 26 06:19 apache2
drwxr-xr-x  1 root                 root                    37 Aug 26 06:27 cron.d
drwxr-xr-x  2 root                 root                    36 Aug 26 05:30 debuginfod
drwxr-xr-x  2 root                 root                    36 Aug 26 05:27 selinux
drwxr-xr-x  2 root                 root                    36 Aug 26 05:31 init
drwxr-xr-x  2 root                 root                    36 Aug 26 05:28 ubuntu-advantage
drwxr-xr-x  2 root                 root                    36 Aug 26 05:27 python3
drwxr-xr-x  2 root                 root                    36 Aug 26 05:31 cracklib
drwxr-xr-x  2 root                 root                    35 Aug 26 06:27 cifs-utils
drwxr-xr-x  3 root                 root                    35 Aug 26 05:29 emacs
drwxr-xr-x  3 root                 root                    35 Aug 26 05:29 xemacs21
drwxr-xr-x  3 root                 root                    35 Aug 26 05:29 glvnd
drwxr-xr-x  2 root                 root                    35 Aug 26 05:31 ipp-usb
drwxr-xr-x  2 root                 root                    35 Aug 26 05:30 sensors.d
drwxr-xr-x  2 root                 root                    35 Aug 26 05:27 cron.hourly
drwxr-xr-x  2 root                 root                    34 Aug 26 05:29 apparmor
drwxr-xr-x  2 root                 root                    34 Aug 26 05:27 depmod.d
drwxr-xr-x  2 root                 root                    34 Aug 26 05:31 kdump
drwxr-xr-x  1 root                 root                    34 Aug 26 06:27 logrotate.d
drwxr-xr-x  2 root                 root                    34 Aug 26 05:30 pcmcia
-rw-r--r--  1 root                 root                    34 Mar 10  2026 ld.so.conf
drwxr-xr-x  2 root                 root                    33 Aug 26 06:27 mdadm
drwxr-xr-x  1 root                 root                    33 Aug 26 06:27 modprobe.d
drwxr-xr-x  2 root                 root                    33 Aug 26 05:33 hp
-r--r--r--  1 root                 root                    33 Nov  1 10:46 machine-id
-rw-r-----  1 root                 root                    33 Aug 26 05:33 brlapi.key
drwxr-xr-x  2 root                 root                    32 Aug 26 05:30 ldap
drwxr-xr-x  2 root                 root                    32 Aug 26 05:30 snmp
drwxr-xr-x  2 root                 root                    32 Aug 26 06:27 cryptsetup-initramfs
drwxr-xr-x  3 root                 root                    31 Aug 26 05:30 ifplugd
drwxr-xr-x  3 root                 root                    31 Aug 26 05:27 ca-certificates
drwxr-xr-x  3 root                 root                    30 Aug 26 05:30 pm
drwxr-xr-x  1 root                 root                    30 Aug 26 05:28 udev
drwxr-xr-x  2 root                 root                    29 Aug 26 05:28 gnutls
drwxr-xr-x  3 root                 root                    29 Aug 26 05:29 alsa
drwxr-xr-x  1 root                 root                    29 Aug 26 05:30 fonts
drwxr-xr-x  2 root                 root                    29 Aug 26 05:27 terminfo
drwxr-xr-x  3 root                 root                    29 Aug 26 05:27 gss
drwxr-xr-x  3 root                 sssd                    29 Aug 26 05:30 sssd
-rw-r--r--  1 root                 root                    27 Jun 12  2024 libao.conf
drwxr-xr-x  2 root                 root                    27 Aug 26 05:33 insserv.conf.d
lrwxrwxrwx  1 root                 root                    27 Aug 26 05:27 localtime -> /usr/share/zoneinfo/Etc/UTC
drwxr-xr-x  3 root                 root                    26 Aug 26 05:29 perl
-rw-r--r--  1 root                 root                    26 Aug 24 10:33 issue
drwxr-xr-x  3 root                 root                    24 Aug 26 05:29 libblockdev
lrwxrwxrwx  1 root                 root                    23 Mar  2  2026 vtrgb -> /etc/alternatives/vtrgb
lrwxrwxrwx  1 root                 root                    21 Aug 24 10:33 os-release -> ../usr/lib/os-release
-rw-r--r--  1 root                 root                    20 Nov  1 10:45 subgid-
-rw-r--r--  1 root                 root                    20 Nov  1 10:45 subuid-
-rw-r--r--  1 root                 root                    20 Feb 20  2025 fprintd.conf
lrwxrwxrwx  1 root                 root                    19 Aug 26 05:27 mtab -> ../proc/self/mounts
-rw-r--r--  1 root                 root                    19 Aug 24 10:33 issue.net
lrwxrwxrwx  1 root                 root                    16 Aug 26 05:27 vconsole.conf -> default/keyboard
lrwxrwxrwx  1 root                 root                    13 Jul 20 13:45 rmt -> /usr/sbin/rmt
-rw-r--r--  1 root                 root                    13 Aug 26 05:28 locale.conf
-rw-r--r--  1 root                 root                    10 Apr 20  2026 debian_version
-rw-r--r--  1 root                 root                     7 Nov  1 10:45 hostname
-rw-r--r--  1 root                 root                     4 Aug 26 05:56 hostid
drwxr-xr-x  2 root                 root                     3 Apr 15  2026 binfmt.d
drwxr-xr-x  2 root                 root                     3 Jul 23 12:34 update-notifier
drwxr-xr-x  2 root                 root                     3 Dec  6  2025 usb_modeswitch.d
drwxr-xr-x  2 root                 root                     3 Aug 26 06:27 keyutils
drwx------  2 root                 root                     3 Apr 15  2026 credstore
drwxr-xr-x  2 root                 root                     3 Aug 26 05:27 opt
drwx------  2 root                 root                     3 Apr 15  2026 credstore.encrypted
drwxr-xr-x  2 gnome-remote-desktop gnome-remote-desktop     3 Aug 26 05:33 gnome-remote-desktop
ubuntu@ubuntu:/etc$ cd ~

