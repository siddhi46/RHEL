*Controlling Access to Files*
r
w
x

//Viewing File & Directory Permission & Ownership
ls -l test

// detail information about directory 
ls -ld /home

// -a permission of hidden files
ls -la

*Managing File System Permissions from the Command Line*

// u,g,o,a user group other all
// + - = add remove set exactly
// r w x read write execute

// 
chmod R g+rwX newdir

// remove read write permission from group and other
chmod go-rw file1

// Changing Permission with Numeric Method
chmod ### file|directory
4 read
2 write
1 execute

chmod 644 file
chmod 750 file

// changing file, directory uder or group ownership
chown student testfile
chown -R student testfile2
chown :admins test_dir

// change group ownership
chown owner:group test

man ls
man chmod
man chown
man chgrp

// Managing Default Permissions and File Access
u+s (suid)
g+s (sguid)
o+t (sticky)

ls -l /usr/bin/passwd
ls -ld /run/log/journal

ls -ld /usr/bin/locate

ls -ld /tmp

// setting special permissions
4 srtuid=u+s;
2 setgid=g+s;
1 sticky=o+t

chmod g+s directory
chmod 2770 directory

// permission of files directories
umask




























