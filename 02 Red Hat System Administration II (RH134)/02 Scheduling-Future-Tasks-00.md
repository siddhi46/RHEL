history -w /dev/stdout

//SCHEDULING FUTURE TASKS

now +5min
teatime tomorrow(teatime is 16:00)
noon +4 day
5pm august 3 2021

nano backup.sh

#!/bin/bash
echo "Backup completed at $(date)" >> /var/log/backup.log

chmod +x backup.sh
at 2:00 AM tomorrow

/path/to/backup.sh


watch atq
cat myjob.txt

atq

at -l

atrm

echo "date" >> /home/atul/Downloads/myjob.txt" | at now +1min

watch atq




at -q g teatime
echo "Its teatime" >> /home/student/tea.txt

at -q b 16:04
echo "the cookies are good" >> /home/student/cookies.txt
atq

at -c 2
echo "its teatime" >> /home/student/tea.txt
at


atq
OR
at -l

at -c JOBNUMBER
atrm

man at
man atd

// SCHEDULING RECURRING USER JOBS
crontab -l
crontab -r
crontab -e
crontab filename


// crontab order:
minutes
hours
day of month
month 
day of week
command

// example:
crontab -e
*/2 08-20 * * Mon-Fri /usr/bin/date >> /home/student/my_first_cron_job.txt
ESC
:wq

while! test -f my_first_cron_job.txt; do sleep 1s; done

cat my_first_cron_job.txt

crontab -r

crontab -l 
 

// example: 15th of every month,and every friday at 12:15
15 12 15 * Fri command


// 0 = sunday, 1= mon, etc.....7 =sun

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name  command to be executed

// /usr/local/bin/yearly_backup | 9AM FEB 2, EVERY YEAR
0 9 2 2 * /usr/local/bin/yearly_backup

// send chime email every fve minutes between 9AM to 5PM on every friday in july.
*/5 9-17 * July 5 echo "Chime"

// /usr/local/bin/daily_report | every weekday at 2 mins before midnight
58 23 * * 1-5 /usr/local/bin/daily_report

// mutt command to send mail checking in boss@example.com on every workday (monday to friday) at 9AM
0 9 * * 1-5 mutt -s "Checking in" boss@example.com % Hi there boss, just checking in.

// SCHEDULING RECURRING SYSTEM JOBS

cat/etc/crontab
cat /etc/cron.d

systemctl daemon-reload
systemctl enable --now 

//

cd /etc/cron.daily/useraccount
vi /etc/cron.daily/useraccount

#!/bin/bash
USERCOUNT=$(w -h | wc-l)
logger "There are currently ${USERCOUNT} active users"

chmod +x /etc/cron.daily/usercount

yum install sysstat

cp /usr/lib/systemd/system/sysstat-collector.timer \
