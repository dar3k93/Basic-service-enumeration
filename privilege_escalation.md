## 1)Searching SUID file (SUID file is a special type of file permission given to a file
find / -perm -u=s -type f 2>/dev/null
find / -perm -4000 -type f 2>/dev/null
find / -uid 0 -perm -4000 -type f 2>/dev/null
find / -type f -perm -g+s -exec ls -ald {} \; 2>/dev/null

## 2)Find world-writeable files excluding proc file
find / ! -path "*/proc/*" -perm -2 -type f -print 2>/dev/null

## 3) Find other users process
ps -aux | grep root

## 4) execute file as root
sudo -l

