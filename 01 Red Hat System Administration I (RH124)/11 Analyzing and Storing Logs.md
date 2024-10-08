history -w /dev/stdout

// From Powershell
ssh -l atul 192.168.31.157

* Analyzing and Storing Logs *

less /var/log
sudo tail /var/log/boot.log

// heart of event logging
journald
rsyslog

journalctl
journalctl _PID=1
journalctl _UID=81

journalctl -n
journalctl -n 5
journalctl -f
journalctl -p err
journalctl -p crit
journalctl -p alert
journalctl -p emerg
journalctl -p warning

journalctl --since today
journalctl --since "2023-11-01 20:20:00" --until ""2023-11-01 20:20:00"
journalctl --since 9:00:00 _SYSTEMD_UNIT="sshd.service"
journalctl --since "-10min"
journalctl --since "-1 hour"

journalctl --o verbose
journalctl _SYSTEMD_UNIT=sshd.service _PID=1182

// Manuals
man systemd.journal-fields
man journalctl
man systemctl.journal-fields
man systemd.time

systemd-journald

ls /var/log

//Selected System Log Files
/var/log/messages
/var/log/secure
/var/log/maillog
/var/log/cron
/var/log/boot.log


// Manuals
man systemd-journald.service
man rsyslogd
man rsyslog.conf

* Reviewing Syslog Files*

/etc/rsyslog.conf
/etc/rsyslog.d

// log file rotation
/var/log
/var/log/messages
/var/log/messages-20231128

man logrotate

// analyzing a syslog entry
time,host,poecess and pid, actual message sent

// Monitering Logs
tail -f /path/to/file

// try 1st terminal
tail -f /var/log/secure

// try second terminal 
ssh root@localhost

// SENDING SYSLOG MESSAGES MANUALLY
logger
logger -p local7.notice "log entry created on host"
cat /var/log/boot.log

// 
systemctl restart rsyslog
logger -p user.debug "Debug Message Test"
tail /var/log/messages-debug

// Manuals
man logger
man tail
man rsyslog.conf
man logrotate

//rsys manual
/usr/share/doc/rsyslog/html/html/indecx.html

// * PRESERVING SYSTEM JOURNAL*
// default system journal
ls /run/log/journal

cat etc/systemd/journald.conf

// persistent, volatile, auto
// persistent
var/log/journal
// volatile
/run/log/journal
//auto : rsyslog determines
/var/log/journal

/etc/systemd/journald.conf
journalctl | grep -E 'Runtime|System journal'

// Configure Persistent System Journals

systemctl restart systemd-journald
ls /var/log/journal
ls /var/log/journal/output-from-pre-command

journalctl -b 1
journalctl -b 2
journalctl -b

// Manuals
man systemd-journald.conf
man systemd-journald

// exercise: 
sudo systemctl restart systemd-journald.service
sudo reboot

sudo ls var/log/journal

// MAINTAINING ACCURATE TIME
timedatectl
tzselect
timedatectl list-timezones
timedatectl set-timezone America/Phoenix
timedatectl
timedatectl set-time 9:00:00
timedatectl
timedatectl set-ntp true
sudo timedatectl set-ntp yes

systemctl restart chronyd
chronyc sources -y


// ANALYZING AND STORING LOGS
timedatectl list-timezones | grep Jamaica
sudo timedatectl set-timezone America/Jamaica
date 
date -d "-30 minutes"
jpurnalctl --since 07:01:00 --until 07:31:00
sudo systemctl restart rsyslog
logger -p authpriv.alert "Logging test authprive.alert"
sudo tail /var/log/auth-errors




