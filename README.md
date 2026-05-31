# Ansible-Playbooks
A collection of Ansible playbooks for automating Linux infrastructure configuration, service management, and system hardening. This repository consists of:

- Playbook directory
- ansible.cfg file
- inventory file 
- jinja file
- .gitignore file

This repository consists of the following sub-directories:

1. web-server-set-up

- This directory consists of:

webdeploy.yml
- installs httpd package, start and enable httpd service, enable firewall for the httpd service, and copy index.html file to the WebServ  er

2. user-management

- This directory consists of :

create_users.yml
- create multiple users in host using the loop

remove-users.yml
- remove users created above using the loop

createusers_vault.yml
- create multiple users in host
- ansible vault is used to create the file where a variable is used to store the username and password
- loop is used to create user and password


