history -w /dev/stdout

ssh -l atul 192.168.31.157

// Creating user and adding password to user
sudo useradd dev
sudo passwd dev

// ssh to user
ssh dev@192.168.31.157
ssh atul@192.168.31.157
// enter password - ("atul" in my case)


// openssh
ssh remotehost
exit
ssh user01@remotehost
ssh newhost

// ssh keygen based authentication
// Generating ssh key 

ssh-keygen
ls /home/atul/.ssh/
cat /home/atul/.ssh/id_rsa

// creating folder key-with-pass
cd /home/atul/.ssh/
touch key-with-pass.pub

// creating passphrase protected private key
ssh-keygen -f .ssh/key-with-pass
// enter keypass ("new" in my case)
cat /home/atul/.ssh/key-with-pass

ssh-copy-id dev@192.168.31.157
ssh-copy-id -i .ssh/key-with-pass.pub dev@192.168.31.157

// Using ssh agent to non-interactive Authentication 
eval $(ssh-agent)

ssh-add
ssh-add .ssh/key-with-pass
// enter keypass ("new" in my case)

ssh -i .ssh/key-with-pass dev@192.168.31.157
// enter keypass ("new" in my case)

*Customizing Openssh Service Configuration*
// Configuring Openssh Server
sudo cat /etc/ssh/sshd_config

// reload ssh server
systemctl reload sshd
systemctl reload sshd.service

// References
man ssh
man ssh_config
