# Ansible-Playbooks
A collection of Ansible playbooks for automating Linux infrastructure configuration, service management, and system hardening. This repository consists of:

## Repository Structure

This repository includes the follwoing files and directories:

- Playbook directory - collection of .yml files for specific automation tasks
- ansible.cfg file - ansible configuration file
- inventory file - Hosts inventory file
- jinja2 template for dynamic configuration
- .gitignore - Git ignore rules

## Directories and Playbooks

###1. web-server-set-up

Contains playbooks to deploy and configure web servers.

  - **'webdeploy.yml'**
    - Installs the httpd package
    - Starts and enables the httpd service
    - Configures the firewall rules to allow HTTP traffic
    - Copies a custom 'index.html' file to the web server host

2. user-management

- This directory consists of :

create_users.yml
- create multiple users in host using the loop

remove-users.yml
- remove users created in create_users.yml using the loop

createusers_vault.yml
- create multiple users in host
- ansible vault is used to create the file where a variable is used to store the username and password
- loop is used to create user and password

createusers_condition.yml
- create multiple users in multiple hosts
- defined multiple variables like DevUsers, WebUsers, TestUsers to include multiple users
- created the users relevant to specific servers like DevUsers in Developer machine, WebUsers in WebServer machine, etc.
- used conditions and loops

removeuses_condition.yml
- remove users created in createusers_condition.yml using different variables than above
- used conditions and loops
