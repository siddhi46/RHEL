// ANALYZING SERVERS AND GETTING SUPPORT

sudo systemctl enable --now cockpit.socket
sudo systemctl status cockpit.service


sudo firewall-cmd --add-service=cockpit --permanent
sudo firewall-cmd --reload

https://servername:9090

ps au

man cockpit
man coxkpit-ws
man cockpit.conf

// DETECTING AND RESOLVING ISSUES WITH RED HAT INSIGHTS

insights-client register
insights-client
subscription-manager register --auto-attach
yum install insights-client
insights-client --register

man insights-client
man insights-clent.conf

https://console.redhat.com/insights/registration/#SIDs=&tags=