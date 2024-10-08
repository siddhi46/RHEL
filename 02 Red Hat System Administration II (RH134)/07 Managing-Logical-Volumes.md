history -w /dev/stdout

// Create a physical volume

pvcreate /dev/vdb2 /dev/vdb1

// Create Volume Group

vgcreate vg01 /dev/vdb2 /dev/vdb1

// Create Logical Volume
lvcreate -n lv01 -L 700M vg01

lvcreate -L 128MB

lvcreate -l 128

mkfs -t xfs /dev/vg01/lv01

mkdir /mnt/data 

mount /mnt/data

lvremove /dev/vg01/lv01

vgremove vg01

sudo pvdisplay

sudo pvdisplay /dev/nvme0n1

pgdisplay

pgdisplay vg01

lvdisplay

vgextend

pvmove

vgreduce
