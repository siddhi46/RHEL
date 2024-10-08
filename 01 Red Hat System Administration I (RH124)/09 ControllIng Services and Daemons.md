Unit 9: Controlling Services and Daemons

# Daemons:Process which either run or wait
# systemd (PID:1)
# .service .socket .path

// list units: loaded and active
systemctl
q

//list available unit types
systemctl -t help

// listing service units
systemctl list-units --type=service
q
systemctl list-units --type=service --all
q

// state of all unit files installed
systemctl list-unit-files --type=service
q

*Viewing Service states*
systemctl status sshd.service
q

// display status of chronyd service (used for Network time synchronization)
systemctl status chronyd


// check main PID
ps -p 1120

// Service Unit Information

| FIELD | DESCRIPTION |

| Loaded | Whether the service unit is loaded into memory |

| Active | Whether the service unit is running and if on how long it has been running |

| Main PID | The main process ID of the service, including the command name. |

| Status | Additional information about the service |


// Several keywords indicating the state of the service can be found in the status output:

Service States in the Output of systemctl 

| KEYWORD | DESCRIPTION |

| loaded | Unit configuration file has been processed. |

| active (running) | Running with one or more continuing processes. |

| active (exited) | Successfully completed a one-time configuration. |

| active (waiting) | Running but waiting for an event. |

| inactive | Not running |

| enabled | is started at boot time. |

| disabled | Is not set to be started at boot time. |

| static | Cannot be enabled, but may be started by an enabled unit automatically. |

// Verifying the status of of a service
systemctl is-active sshd.service
systemctl is-enabled sshd.service
systemctl is-failed sshd.service

systemctl is-active bluetooth.service
systemctl is-enabled bluetooth.service
systemctl is-failed bluetooth.service

*Controlling System Services*
//starrting and stopping services
systemctl start sshd.service
OR
systemctl start sshd
systemctl stop sshd.service

// Check sshd status
systemctl status sshd

// restarting and reloading services
systemctl restart sshd.service
systemctl reload sshd.service
systemctl reload-or-restart sshd.service

// Listing Unit Dependencies
systemctl stop cups.service
systemctl list-dependencies sshd.service
q

// Example:Installing and Setting up Sendmail

// Masking and Unmasking services
systemctl mask sendmail.service
systemctl list-unit-files --type=service
systemctl start sendmail.service
systemctl unmask sendmail

//Enable service to start and boot
systemctl enable sshd.service
systemctl disable sshd.service

// Enable cockpit console
systemctl enable --now cockpit.socket

// Useful Service Management Commands
systemctl status UNIT
systemctl stop UNIT
systemctl start UNIT
systemctl restart UNIT
systemctl reload UNIT
systemctl mask UNIT
systemctl unmask UNIT
systemctl enable UNIT
systemctl disable UNIT
systemctl list-dependencies UNIT

//References
man systemd
man systemd.unit
man systemd.service
man systemd.socket
man systemctl

// Examples
systemctl status psacct
sudo systemctl start psacct
sudo systemctl is-active psacct
sudo systemctl enable psacct

systemctl status rsyslog
sudo systemctl start rsyslog
sudo systemctl stop rsyslog
sudo systemctl is-active rsyslog
sudo systemctl is-enabled rsyslog
sudo systemctl enable rsyslog
sudo systemctl disable rsyslog









