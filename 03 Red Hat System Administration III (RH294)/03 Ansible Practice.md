history -w /dev/stdout

ansible all --list-hosts
ansible ungrouped --list-hosts
ansible webservers --list-hosts
ansible databaseservers --list-hosts
ansible dev --list-hosts
ansible test --list-hosts
ansible qa --list-hosts
ansible --version

ansible all -vvv -m ping

ssh -vvv -i ansiblekey.pem ec2-user@54.173.215.13

ansible-playbook playbook.yml -f 10