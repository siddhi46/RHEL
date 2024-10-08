history -w /dev/stdout

// users and groups
id
id atul
id user0
id user1
ls
ls -l
ls -ld
ls -l test.py
ls -ld test.py

touch file
touch folder
ls -l file
ls -ld folder

cat /etc/group

// gaining superuser access
su

Managing Local Users & Groups

// info of logged in users
id
id user02
// check owner of the file
ls - l file1
ls - ld dir1

//process information
ps - au

/etc/passwd
/etc/shadows
/etc/group

//gaining superuser access
su
su - user02
su -
sudo usermod - L user02
sub - user02
sudo tail /var/log/secure
sudo - i
sudo - s

// Configure Sudo
/etc/sudoers

%wheel     ALL=(ALL)        ALL

// Enable full sudo access for user01
/etc/sudoers.d/user01

user01 ALL=(ALL) ALL

// Enable full sudo grouo01
/etc/sudoers.d/group01

%group01 ALL=(ALL) ALL

ansible ALL=(ALL) NOPASSWD:ALL

ec2-user ALL(ALL) NOPASSWD: ALL

//sudo - i behave more like su - by editing /etc/sudoers with visudo

Defaults secure_path = /sbin:/bin:/usr/sbin:/usr/bin

Defaults secure_path = /usr/local/bin:usr/bin
Defaults>root secure_path = /usr/local/sbin:usr/local/bin:/usr/sbin:/usr/bin

man su
man sudo
man visudo
man sudoers

//managing local user accounts | Usermod Options
-c, --comment COMMENT
-g, --gid GROUP
-G, --groups GROUPS
-a, --append
-d, --home HOE_DIR
-m, --move-home
-s, --shell SHELL
-L, --lock 
-U, --unlock 

useradd user01
ls -l /home
userdel user01
ls -l /home
useradd user02
ls -l /home

// unowned files and directory
find / -nouser -o -nogroup

passwd user01

UID0 -root
UID 1-200 	system Users
UID 1000+ regular users

man useradd
man usermod
man userdel

Managing Local Users & Groups

// info of logged in users
id
id user02
// check owner of the file
ls - l file1
ls - ld dir1

//process information
ps - au

/etc/passwd
/etc/shadows
/etc/group

//gaining superuser access
su
su - user02
su -
sudo usermod - L user02
sub - user02
sudo tail /var/log/secure
sudo - i
sudo - s

// Configure Sudo
/etc/sudoers

%wheel     ALL=(ALL)        ALL

// Enable full sudo access for user01
/etc/sudoers.d/user01

user01 ALL=(ALL) ALL

// Enable full sudo grouo01
/etc/sudoers.d/group01

%group01 ALL=(ALL) ALL

ansible ALL=(ALL) NOPASSWD:ALL

ec2-user ALL(ALL) NOPASSWD: ALL

//sudo - i behave more like su - by editing /etc/sudoers with visudo

Defaults secure_path = /sbin:/bin:/usr/sbin:/usr/bin

Defaults secure_path = /usr/local/bin:usr/bin
Defaults>root secure_path = /usr/local/sbin:usr/local/bin:/usr/sbin:/usr/bin

man su
man sudo
man visudo
man sudoers

*Managing User Passwords*

// Check files /etc/passwd  & /etc/shadow

// Configuring password aging

sudo chage -m 0 -M 90 -W 7 -I 14 user03

// Restrict access to user 

sudo usermod -L user03
su - user03

sudo usermod -L -e 2019-10-05 user03

/sbin/nologin

// Managing Local Group Accounts
sudo groupadd -g 10000 group01
tail /etc/group

// -r creates system group using GID /etc/login.def
sudo groupadd -r group02
tail /etc/group

// modifying existing groups from CLI
sudo groupmod -n group0022 group02
tail /etc/group

// -g specifies new gid
sudo groupmod -g 20000 group0022
tail /etc/group

// Deleting Groups from CLI
sudo groupde1 group0022

// Changing group membership from CLI
id user02
sudo usermod -g group01 user02
id user02

// deleting user from group 

sudo gpasswd bob systemadmin2
sudo gpasswd --delete bob systemadmin2
sudo gpasswd --delete lily systemadmin2

// use usermod -G 
// add user to supplimentary group
id user03
sudo usermod -aG group01 user03
id user03 