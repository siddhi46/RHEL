history -w /dev/stdout

touch reports.txt
ls -l
chmod 777 reports.txt
ls -l
// to display acl settings on file
getfacl reports.txt
// view directory acl
getfacl .

man acl
man getfacl
man journald.conf
man ls
man systemd-journald
man systemd-udevd

touch new.txt
mkdir folder
setfacl -m u:atul:rw new.txt

man acl
man setfacl
man getfacl