history -w /dev/stdout

// From Powershell
ssh -l atul 192.168.31.157

* MANAGING NETWORKING *
TCP/IP NETWORK MODEL
- Application
- Transport /etc/services
- Internet
- Link

// DESCRIBE NETWORK INTERFACE NAMES

// IPV4 NETWORKING
// IPV4 Addresses
// IPV4 Routing and Configuration
// IPV6 NETWORKING
// IPV6 Addresses
// IPV6 Subnetting
// IPV6 Address Configuration
// Host Names and IP Addresses

cat /etc/hosts

// Manuals
man services
man ping
man biosdevname
man udev


// VALIDATING NETWORK CONFIGURATIONS
// list all network interfaces 
ip link
ip link show

// Displaying IP Addresses
ip addr
ip addr show
ip addr show lo
ip addr show ens160

// displaying performance statistics
ip -s link show ens160

// Chec connectivity Between Hosts
ping -c3 192.0.2.254
ping6 2001:db8:0:1::1
ping6 ff02::1%ens4
ping6 -c 1fe80::f482:dbff:fe25:6a9f%ens4
ssh 1fe80::f482:dbff:fe25:6a9f%ens4

// Troubleshooting Routing Table
ip route
ip -6 route


// Tracing Routes Taken by Traffic
tracepath access.redhat.com
tracepath6 2001:db8:0:2::451

// Troubleshooting Ports and Services
// Display socket statistics

ss -ta
ss -n
ss -t
ss -u
ss -l
ss -a
ss -p
ss -A net
ss -lt


// Manuals
man ip-link
man ip-address
man ip-route
man ip
man ping
man tracepath
man traceroute
man ss
man netstat

* CONFIGURING NETWORKING FROM CLI*
ls /etc/sysconfig/network-scripts
cat /etc/sysconfig/network-scripts/readme-ifcfg-rh.txt

// Viewing Network Information
nmcli dev status
nmcli con show
nmcli con show --active
nmcli con show name
nmcli con add con-name name
nmcli con mod name
nmcli con reload
nmcli con up name
nmcli dev dis dev
nmcli con del name


//Controlling Networking Connections
nmcli con up static-ens3
nmcli dev dis ens3

nmcli con show
nmcli con show ens160
nmcli con show static-ens160

// Manuals
man NetworkManager
man nmcli
man nmcli-examples
man nm-settings
man hostnamectl
man resolv.conf
man hostname
man ip
man ip-address

// EDITING NETWORK CONFIGURATION FILES
nmcli con reload
nmcli con down "static-ens3"
nmcli con up "static-ens3"

man nmcli


// CONFIGUREING HOSTNAMES AND NAME RESOLUTION
// Change Hostname
sudo hostname
hostnamectl set-hostname host@example.com
hostnamectl status
cat /etc/hostname

// Configure Name Resolution
cat /etc/hosts
sudo nano /etc/hosts
cat /etc/resolv.conf

host class
getent hosts class

// Manuals
man nmcli
man hostnamectl
man hosts
man getent
man host
man resolv.conf





