history -w /dev/stdout

// Building Ansible Inventory

sudo vim/nano /etc/ansible/hosts

web1.example.com
web2.example.com
db1.example.com
db2.example.com
192.0.2.42

ansible all --list-hosts
ansible ungrouped --list-hosts
ansible webservers --list-hosts
//

[webservers]
web1.example.com
web2.example.com

[db-servers]
db1.example.com
db2.example.com

// 
[webservers]
web1.example.com
web2.example.com

[db-servers]
db1.example.com
db2.example.com

[east-datacenter]
web1.example.com
db1.example.com

[west-datacenter]
web2.example.com
db2.example.com

[production]
web1.example.com
web2.example.com
db1.example.com
db2.example.com

[developement]
192.0.2.42

// nested group
[usa]
washington1.example.com
washington2.example.com

[canada]
ontario01.example.com
ontario02.example.com

[north-america:children]
canada
usa

// Simplifying host specification with ranges
// [START:END]

[usa]
washington[1:2].example.com

[canada]
ontario[01:02].example.com

ansible washington1.example.com --list-hosts
ansible washington01.example.com --list-hosts

ansible canada --list-hots

/etc/ansible/hosts

sudo vim/nano /etc/ansible/hosts


// Create a static inventory  
mkdir /home/atul/deploy-inventory
nano inventory

[webservers]
server[a:d].lab.example.com

[raleigh]
servera.lab.example.com
serverb.lab.example.com

[mountainview]
serverc.lab.example.com

[london]
serverd.lab.example.com

[developement]
servera.lab.example.com

[testing]
serverb.lab.example.com

[production]
serverc.lab.example.com
serverd.lab.example.com

[us:children]
raleigh
mountainview


//
ansible all -i inventory --list-hosts
ansible ungrouped -i inventory --list-hosts
ansible development -i inventory --list-hosts
ansible testing -i inventory --list-hosts
ansible production -i inventory --list-hosts
ansible us -i inventory --list-hosts