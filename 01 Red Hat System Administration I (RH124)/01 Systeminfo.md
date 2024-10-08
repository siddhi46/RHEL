// gather system information

lscpu //CPU
lsblk //Disk
lsusb //USB
sudo dnf install -y usbutils
lsusb
lspci //PC Devices
sudo dnf install -y pciutils

v  more detailed output, 
-k list the Linux kernel module in use by the device
-s filter specific devices based on their ID.

example:  list kernel modules for device 05:00.0, use:
lspci -s 05:00.0 -k

//RAM
free -m
sudo dnf install -y dmidecode //Detail

//BIOS
sudo dmidecode -t bios

//System Info
sudo dmidecode -t system

