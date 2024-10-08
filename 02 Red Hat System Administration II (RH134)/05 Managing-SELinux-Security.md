history -w /dev/stdout

setenforce Enforcing
OR
sudo setenforce 1
getenforce
setenforce Permissive 
OR 
sudo setenforce 0getenforce



ps axZ
sudo systemctl start httpd
ps -ZC httpd
ls -Z /home
ls -Z /var/www

# // Changing Current SELinux Mode
sestatus
getenforce
setenforce
setenforce 0
sudo setenforce 0
getenforce
setenforce Enforcing
sudo setenforce Enforcing
getenforce
sudo nano /etc/selinux/config
sudo vi /etc/selinux/config
sestatus
getenforce

# // Set the default SELinux Mode
SELINUX=enforcing
SELINUX=targeted
man getenforce
man setenforce
man selinux_config

sudo semanage login -l
// list users
seinfo -u
seinfo -r

sudo seamanage boolean -l

id -Z
ps axZ
ps -a
sudo systemctl status httpd
sudo systemctl enable httpd

sudo semanage port -l | grep http
sudo semanage port -a -t http_port_t -p tcp 3131
sudo semanage port -l | grep http
sudo systemctl start httpd
cd /var/www/html
sudo nano index.html
```
<h1> This is Webserver </h1>
```
```
http://localhost:80
```

pwd
ls
semanage port -a -t http_port_t -p tcp 3131
sudo semanage port -a -t http_port_t -p tcp 3131
systemctl start httpd
wget localhost:3131/index.html