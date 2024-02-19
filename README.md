# Ansible Playbook for Server Configuration

This Ansible playbook automates the configuration of servers, including installing Python 3, configuring Nginx, Fail2Ban, PM2, and obtaining and configuring SSL certificates using Certbot.

## Prerequisites
- Ansible installed on your local machine
- SSH access to the target servers
- Proper inventory file containing the IP addresses of your servers

## Usage
1. **Inventory Setup**: Ensure that your Ansible inventory file contains the correct IP addresses of your servers.
2. **SSH Key Setup**: Make sure you have SSH access to the servers, and your SSH private key is properly configured.
3. **Run the Playbook**: Execute the playbook using the following command:

Replace `Key.yml` with your inventory file and `playbook.yml` with the name of your playbook file.

## Playbook Structure
- **Play 1**: Install Python 3 on the remote server.
- Update package cache and install Python 3.

- **Play 2**: Configure Nginx, Fail2Ban, and PM2 on the server.
- Update apt cache, install required packages, start and enable Nginx and Fail2Ban services, and install PM2 using npm.

- **Play 3**: Install Certbot and obtain SSL certificates on the server.
- Install Certbot package based on the OS distribution, obtain SSL certificates using Certbot.

- **Play 4**: Configure automatic renewal for SSL certificates on the server.
- Create Certbot renewal configuration for automatic certificate renewal.

**Note**: Make sure to replace placeholders such as `yourdomain.com` with your actual domain name in the SSL certificate tasks. Uncomment and customize handlers if required for reloading Nginx.

