Ansible


Ansible is a popular configuration management tool which uses SSH connection to their host to do tasks which is agentless

Main config file of Ansible

/etc/ansible/hosts

[web_servers]
web1 ansible_host=192.168.1.101 ansible_user=your_username ansible_ssh_private_key_file=/path/to/your/private_key


Replace web1 with your desired hostname, 192.168.1.101 with the actual IP address of your server, your_username with your SSH username, and /path/to/your/private_key with the path to your private SSH key.

If you have multiple hosts, you can add more entries under and group it group:


Create an inventory file (e.g., inventory.ini) with the list of servers you want to check and create an ansible playbook with  Shell or Command module with free -mh command

also

define  hosts in  my_inventory.ini

contain code tasks to do:  my_playbook.yml


ansible-playbook -i my_inventory.ini my_playbook.yml


Example for an ad-hoc command 

ansible all -m ping

ansible-playbook -i my_inventory.ini 


[root@git-server ~]# ansible-galaxy init nginx
- Role nginx was created successfully
[root@ansible-server ~]# 
[root@ansible-server nginx]# tree /root/nginx/
/root/nginx/
├── README.md
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── tasks
│   └── main.yml
├── templates
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml

8 directories, 8 files

[root@ansible-server nginx]#

tasks: Contains the main YAML file where you define the tasks to be executed.

handlers: Contains YAML files defining handlers, which are tasks that respond to a notification triggered by other tasks.

templates: Contains template files, which can be used with the template Ansible module to generate dynamic content.

vars: Contains variable files.


