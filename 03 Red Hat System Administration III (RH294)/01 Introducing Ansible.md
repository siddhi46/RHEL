history -w /dev/stdout

//IaC

# Crosscheck RHEL System info
cat /etc/redhat-release

- First register your system to RHSM:
# subscription-manager register

OR In Case System is not registered | You can register the system using
subscription-manager register --username your-username --password Your-Password@123 --auto-attach
subscription-manager register --username your-username --password Your-Password@123 --auto-attach --force

# subscription-manager role --set="Red Hat Enterprise Linux Server"

- Attach your Red Hat Ansible Automation Platform subscription.  This command will help you find the Red Hat Ansible Automation Platform subscription:
# subscription-manager list --available

- Grab the pool id of the subscription and run the following:
# subscription-manager attach --pool=<pool id here of ansible subscription>

- Enable the Red Hat Ansible Engine Repository:
# subscription-manager repos --enable rhel-7-server-ansible-2-rpms
# subscription-manager repos --enable ansible-2-for-rhel-8-x86_64-rpms

#see valid repositories
subscription-manager repos --list

# subscription-manager repos --enable ansible-automation-platform-2.2-for-rhel-9-x86_64-rpms
# subscription-manager repos --enable ansible-automation-platform-2.3-for-rhel-9-x86_64-source-rpms

sudo yum install ansible -y

subscription-manager refresh

sudo yum install python

ansible --version

ansible -m setup localhost | grep ansible_python_version
