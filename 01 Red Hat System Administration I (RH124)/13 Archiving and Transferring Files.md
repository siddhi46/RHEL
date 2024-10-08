history -w /dev/stdout

// From Powershell
ssh -l atul 192.168.31.157

* Archiving & Transferring Files *

tar
-c, - - create
-x, - - extract
-t, - - list
-v, - - verbose
-f, - - file=
-p, - - preserve-permissions
-z, - - gzip
-j, - - bzip2
-J, - - xz

// Practice
touch a.txt
touch b.txt
touch test.py
ls
tar simple.tar a.txt b.txt test.py
tar -cf simple.tar a.txt b.txt test.py
ls
ls simple.tar
tar -xf simple.tar

//
tar - cf archive.tar file1 file2 file3
OR
tar - - file=achieve.tar - - create file1 file2 file3
ls archive.tar

tar - cf /root/etc.tar /etc

//listing contents of archive
tar - tf /root/etc.tar

//Restore files to backup directory
mkdir /root/etcbackup
cd /root/etcbackup
tar -tf /root/etc.tar
tar -xf /root/etc.tar

Example:
mkdir /root/scripts
cd /root/scripts
tar - xpf /root/myscripts.tar

// CREATING A COMPRESSED ACHIEVE
-z or - - gzip
-j or - - bzip2
-J or - xz

tar - czf /root/backup.tar.gz /etc

tar - cjf /root/lookbackup.tar.bz2 /var/log

tar - cJf /root/sshconfig.tar.xz /etc/ssh

tar - tf /root/etcbackup.tar.gz /etc

// EXTRACTING A COMPRESSED ACHIEVE
*TRANSFERING FILES USING SECURE COPY*
scp /etc/yum.conf /etc/hosts remoteuser@remotehost:/home/remoteuser

scp remoteuser@remotehost:/etc/hostname /home/user
// scp dev@localhost:/etc/hostname /home/atul/Downloads/new.tar

scp -r root@remoteuser:/var/log /tmp

sftp remoteuser@remotehost


Example:
mkdir hostbackup
cd hostbackup
put /etc/hosts

get /etc/yum.conf
exit

/SYNCHRONISING FILES BETWEEN SYSTEMS SECURELY
-r,--recursive
-l,--links
-p, --perms
-t,--times
-g,--group
-o,--owner
-D, --devices
-A,to reserve ACLs
-X, preserve SELinux Context

su -
pssword
rsync -av /var/log /tmp
ls /tmp

rsync -av /var/log/ /tmp
ls /tmp

rsync -av /var/log remotehost:/tmp
password

rsync -av remotehost:/var/log /tmp
password

man rsync


