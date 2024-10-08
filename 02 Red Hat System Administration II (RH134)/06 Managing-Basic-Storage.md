history -w /dev/stdout

history -w /dev/stdout

sudo parted

(parted) help
  align-check TYPE N                       check partition N for TYPE(min|opt) alignment
  help [COMMAND]                           print general help, or help on COMMAND
  mklabel,mktable LABEL-TYPE               create a new disklabel (partition table)
  mkpart PART-TYPE [FS-TYPE] START END     make a partition
  name NUMBER NAME                         name partition NUMBER as NAME
  print [devices|free|list,all]            display the partition table, or available devices, or
        free space, or all found partitions
  quit                                     exit program
  rescue START END                         rescue a lost partition near START and END
  resizepart NUMBER END                    resize partition NUMBER
  rm NUMBER                                delete partition NUMBER
  select DEVICE                            choose the device to edit
  disk_set FLAG STATE                      change the FLAG on selected device
  disk_toggle [FLAG]                       toggle the state of FLAG on selected device
  set NUMBER FLAG STATE                    change the FLAG on partition NUMBER
  toggle [NUMBER [FLAG]]                   toggle the state of FLAG on partition NUMBER
  type NUMBER TYPE-ID or TYPE-UUID         type set TYPE-ID or TYPE-UUID of partition NUMBER
  unit UNIT                                set the default unit to UNIT
  version                                  display the version number and copyright information of
        GNU Parted
(parted)


sudo parted /dev/nvme0n1 print

sudo parted /dev/nvme0n1 mklabel msdos

sudo parted /dev/nvme0n1 mklabel gpt


sudo parted /dev/nvme0n1 print


sudo parted /dev/nvme0n1 help mkpart

2048s

1000MB

xfs


print 


rm 1

mkfs.xfs /dev/nvme0n1

mount /dev/nvme0n1 /mnt

man parted 
man mkfs
man mount
man lsblk
man fstab


// Managing Swap Space

parted /dev/nvme0n1

mkpart 
swap
linux-swap

udevadm settle

mkswap /dev/nvme0n1
swapon --show


systemctl daemon-reload


man mkswap
man swapon
man swapoff
man mount
man parted

