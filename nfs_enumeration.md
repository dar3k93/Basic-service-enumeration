### Network File Sytem (NFS)
- The Network File System (NFS) is a client/server application that lets a computer user view and optionally store and update files on a remote computer as though they were on the user's own computer. The NFS protocol is one of several distributed file system standards for network-attached storage (NAS).
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Basic Command
- showmount [ip]

- create temp local folder
```
mkdir /tmp/nfs
```
- mount
```
mount -t nfs [ip]:/home/vulnix /tmp/nfs -nolock
```
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### nmap 
```
nmap -sV --script=nfs-showmount [victim_ip]
```