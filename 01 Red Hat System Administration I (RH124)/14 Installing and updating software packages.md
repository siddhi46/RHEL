*INSTALLING AND UPDATING SOFTWARE PACKAGES*
//Redhat Subscription Management
subscription-manager register --username=yourusername --password=yourpassword

sudo subscription-manager register --username=atul_kamble --password=LEJ@5

sudo subscription-manager register --username=atul_kamble --password=LutaElbmakJ@5 --force

sudo subscription-manager list --available | less

sudo subscription-manager attach --auto

sudo subscription-manager attach --pool=poolID

sudo subscription-manager list --consumed

sudo subscription-manager unregister

man subscription-manager

// EXPLAINING AND INVESTIGATION RPM SOFTWARE PACKAGES

coreutils-8.30-4.el8.x86_64.rpm

// lsiat all installed packages
rpm -qa

// find out kg provides filename
rpm -qf /etc/yum.repos.d

// listr what version of package installed
rpm -q 
rpm -q yum

// get detailed information
rpm -qi
rpm -qi yum


// list files installed by package
rpm -ql yum

// list configuration files installed by package
rpm -qc openssh-clients

// list just adocumentation files installed by the package
rpm -qd openssh-clients

// list shell scripts that run before and after package is installed/removed.
rpm -q --scripts openssh-server

// list change information for the package
rpm -q --changelog audit

* INSTALLING RPM PACKAGES*
rpm -ivh wonderwidgets-1.0-4.x86_64rpm

*INSTALLING AND UPDATING SOTWARE PACKAGES WITH YUM*

// finding software with yum
yum help
yum list 'http*'
yum search all 'web server'
yum search guile
yum info httpd
yum info guile
yum provides /var/www/html
yum install httpd
yum install -y guile
yum remove guile
yum remove gc
sudo yum remove httpd


sudo yum update
yum update kernel
yum list kernel
uname -r
uname -a

// software groups
yum group list
yum group info "RPM Development Tools"
sudo yum group install "RPM Development Tools"

// Viewing Transaction History
tail -5 /var/log/dnf.rpm.log

// yum history
sudo yum history
yum history info 6
sudo yum history undo 5

// Man Pages
man yum
man yum.conf

*ENABLING YUM SOFTWARE REPOSITORIES*
yum repolist all
yum-config-manager --enable rhel-8-server-debug-rpms

*MANAGING PACKAGE MODULE STREAMS*
yum module list
yum module list --installed
yum module list perl
yum module info python36
yum module list python36
yum module install list postgresql
yum module install list postgresql:10
yum module info perl
yum module info --profile perl:5.24
sudo yum module install -y perl
yum module list perl
sudo yum module remove -y perl
yum module list perl
sudo yum module disable perl
sudo yum module install perl:5.24
 




















