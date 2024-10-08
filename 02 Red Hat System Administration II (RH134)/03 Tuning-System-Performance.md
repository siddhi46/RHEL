history -w /dev/stdout

# TUNING SYSTEM PERFORMANCE
# // Install and enabling Tuned
sudo yum install tuned -y
tuned --version
yum list tuned
sudo systemctl enable --now tuned
sudo systemctl is-enabled tuned
sudo systemctl is-active tuned

# // Managing Profiles from Command Line
tuned-adm active
tuned-adm list
sudo tuned-adm profile powersave
sudo tuned-adm active
tuned-adm profile aws
sudo tuned-adm profile aws
tuned-adm active
tuned-adm recommend
sudo tuned-adm profile virtual-guest
tuned-adm off
tuned-adm active

# // Influecing Process Scheduling
ps axo pid,comm,nice,cls --sort=nice
# //Starting processes with different nice level
sha1sum /dev/zero &
ps -o pid,comm,nice 14506
# // example:
nice sha1sum /dev/zero &
ps -o pid,comm,nice 14535
nice -n 15 sha1sum &
ps -o pid,comm,nice 14555
#// Changing nice level of an existing process
renice -n 19 14555
man nice
man renice
man top
man sched_setscheduler

jobs
ps u
pkill sha1sum

