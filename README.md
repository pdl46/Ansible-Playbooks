# Ansible Playbooks

A comprehensive collection of Ansible playbooks for automating Linux infrastructure configuration, service management, and system hardening.

## Repository Structure

This repository includes the following key components:

- `ansible.cfg` — Ansible configuration file  
- `inventory` — Hosts inventory file  
- Jinja2 templates for dynamic configuration  
- `.gitignore` — Git ignore rules  
- Playbook directories organized by functionality  

## Directory Overview

### 1. web-server-set-up

Playbooks for deploying and configuring web servers.

- **`webdeploy.yml`**  
  - Installs the Apache HTTP Server (`httpd`) package  
  - Starts and enables the `httpd` service  
  - Configures firewall rules to allow HTTP traffic  
  - Deploys a custom `index.html` file to the web server root  

### 2. user-management

Playbooks for managing user accounts with advanced features.

- **`create_users.yml`**  
  - Creates multiple user accounts on hosts using loops  

- **`remove-users.yml`**  
  - Removes users created by `create_users.yml`  

- **`createusers_vault.yml`**  
  - Creates users with credentials securely stored using Ansible Vault  
  - Uses variables for usernames and passwords  
  - Loops through user creation and password assignment  

- **`createusers_condition.yml`**  
  - Creates users on multiple hosts based on user groups such as `DevUsers`, `WebUsers`, `TestUsers`  
  - Assigns users to relevant servers using conditional logic and loops  

- **`removeusers_condition.yml`**  
  - Removes users created by `createusers_condition.yml`  
  - Uses conditions and loops for precise user removal  

### 3. file-management

- **`user_files.yml`**
  - Creates a touch file in hosts with user permissions defined
  - Enables SE Linux on the file

### 4. service-management

- **`userpackage.yml`**
  - Creates multiple users and packages in multiple hosts
  - Eg: CloudEngineer user in Developer host, httpd package in WebServer host, etc.

- **`multiplepackages.yml`**
  - Defines a separate variable for each of the packages
  - Installs packages using the variables defined above in WebServer host

- **`removepackages.yml`**
  - Defines a single variable list for all of the packages
  - Removes the packaes installed through multiplepackages.yml using a loop

- **`debugvariable.yml`**
  - Installs mariadb package in Developer machine
  - Uses the register variable to print the infomration using debug module

- **`handlers_mariadb.yml`**
  - Installs mariadb server in WebServer machine
  - Starts and enables the mariadb service
  - Copies the mariadb conf file to remote host
  - Uses handlers to restart the mariadb server only when conf file is changed

- **`templatemodule.yml`**
  - Uses a template module to copy the jina2 file to the Developer machine

### 4. firewall-config

- **`removehttpd.yml`**
  - Stops and Disable httpd service
  - Disables firewall for httpd service
  - Removes httpd package
  - Removes index.html file from remote host
