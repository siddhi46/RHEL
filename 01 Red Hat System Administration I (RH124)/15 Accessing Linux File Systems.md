Accessing Linux File Systems

df   // disk space used disk space 
df -h
du usr/share
du -h /var/log
/run/media

// Mount and Unmount File Systems

// Identify Block Devices
lsblk
mount /dev/vbd1 /mnt/data

lsblk -fp

unmount /mnt/data

cd /mnt/data
unmount /mnt/data

lsof /mnt/data

cd
unmount /mnt/data

man lsblk
man mount
man umount
man lsof

// LOCATING FILES ON THE SYSTEM
updatedb
locate passwd
locate image
locate -i messages
locate -n 5 snow.png


//Searching for files in Real Time
find / -name sshd_config
find / -name '*.txt'
find /etc -name '*pass*'
find / -iname '*messages*'

// Searchinf files Based on Ownership or Permission
find -user user
find -group user
find -uid 1000
find -gid 1000
find / -user root -group mail
find /home -perm 764
find /home -perm -324
find /home -perm /442
find -perm -004
find -perm -002


//Seraching files based on size
find -size 10M
find -size +10G
find -size 10k
find / -mmin 120
find / --mmin +200
find / -mmin -150

//Searching file based on file type
find /etc -type d
find / -type l
find /dev -type b
find / -type f -links +1

man locate
man updatedb
man find









