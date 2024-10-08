// Monitoring and Managing Linux  Processes

// Process: Running instance of executable program

top
//q 

// display all processes
ps aux 

// display with technical details
ps lax

// unix syntax
ps -ef

*Controlling Objects*
sleep 10000 &

jobs

fg %1

[cntrl+Z]

// display information related to jobs
ps j

bg %1

*Killing Processes*
kill -l

ps aux | grep job
kill 11584
ps -a

ps aux | grep job
killall control

ps aux | grep pkill

pkill control

ps aux | grep pkill

ps aux | grep test

pkill -U user
ps aux | grep test

//Logging users out administratevely

// list only usernames
awk -F':' '{ print $1}' /etc/passwd

// find pid numbers to be killed by pgrep
pgrep -l -u atul

pkill -SIGKILL -u atul
pgrep -l -u atul

pgrep -l -u atul
w -h -u atul
pkill -t tty3
pgrep -l -u atul
pkill SIGKILL -t tty3
pgrep -l -u atul

//Process Tree
pstree -p atul
pkill -P 8391
pgrep -l -u atul
pkill SIGKILL -P 8391
pgrep -l -u atul

man kill
man killall
man pgrep
man pkill
man pstree
man signal
man w

*Monitering Process Activity*
uptime
lscpu
moniter &
cpuinfo

ps jT






