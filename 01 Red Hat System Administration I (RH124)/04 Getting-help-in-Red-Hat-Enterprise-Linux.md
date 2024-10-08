history -w /dev/stdout

// Getting Help in RHEL
man

// TH: Common Sections of Linux Manual
user commands
system calls
library functions
special files
file formats
games
conventions,standards and miscellaneous
system administration and priviledged commands
linux kernel API

// man
man
man man
q
man passwd
man -k passwd //search man pages by keyword

whereis passwd
whereis man
man -k zip
man -k boot
man -k ext4

// create formatted file of passwd man page
man -t passwd > passwd.ps
ls -al
pwd
file /home/ec2-user/passwd.ps
less /home/ec2-user/passwd.ps
q
man -k postscript viewer
man evince

