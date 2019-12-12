#### Check kernel version
- uname -a
- cat /proc/version
- cat /etc/issue

#### Check common location for user installed software
- /usr/local/
- /usr/local/src
- /usr/local/bin
- /opt/
- /home
- /var/
- /usr/src/

#### Available services
- netstat -anlp
- netstat -ano

#### Unmounted filesystem
- mount -l
- cat /etc/fstab

#### Searching SUID file (SUID file is a special type of file permission given to a file
- find / -perm -u=s -type f 2>/dev/null
- find / -perm -4000 -type f 2>/dev/null
- find / -uid 0 -perm -4000 -type f 2>/dev/null
- find / -type f -perm -g+s -exec ls -ald {} \; 2>/dev/null

#### Find world-writeable files excluding proc file
find / ! -path "*/proc/*" -perm -2 -type f -print 2>/dev/null

#### Find other users process
ps -aux | grep root

#### Find 
find / -exec /usr/bin/awk 'BEGIN {system("/bin/bash")}' ;

#### Find world writable files
find / -writable -type d 2>/dev/null
find / -perm -222 -type d 2>/dev/null
find / -perm -o w -type d 2>/dev/null
##### Find world writable folder
find / -perm -o x -type d 2>/dev/null
##### Find world writable and executable folders
find / \( -perm -o w -perm -o x \) -type d 2>/dev/null

#### Execute file as root
sudo -l

#### World writable directories
/tmp
/var/tmp
/dev/shm
/var/spool/vbox
/var/spool/samba

#### Cronjobs
- crontab -l
- ls -alh /var/spool/cron
- ls -al /etc/ | grep cron
- ls -al /etc/cron*
- cat /etc/cron*
- cat /etc/at.allow
- cat /etc/at.deny
- cat /etc/cron.allow
- cat /etc/cron.deny
- cat /etc/crontab
- cat /etc/anacrontab
- cat /var/spool/cron/crontabs/root

#### Run usefull script for linux enumeration
- ***Linenum***: https://github.com/rebootuser/LinEnum
- ***Linuxprivchecker***: https://github.com/sleventyeleven/linuxprivchecker/blob/master/linuxprivchecker.py
- ***LinuxExploitSuggester***: https://github.com/mzet-/linux-exploit-suggester
- ***LinuxExploitSuggester2***: https://github.com/jondonas/linux-exploit-suggester-2
- ***LinuxPrivChecker***: https://github.com/sleventyeleven/linuxprivchecker/blob/master/linuxprivchecker.py
- ***LinuxSmartEnumeration***: https://github.com/diego-treitos/linux-smart-enumeration

#### 6) Enumerate /var directory and uncommon files and directory names

