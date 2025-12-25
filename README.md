
# Ansible DevOps Projects

This repository contains real-world Ansible projects for automating Linux server setup, configuration management, and basic security hardening. 

## Structure

- **inventories/**: dev/prod environment inventories
- **playbooks/**: Playbooks to run Roles
- **roles/**: Reusable Roles
  - **common**: Base server setup (update, basic packages)
  - **nginx**: Install and configure Nginx with handler
  - **security**: SSH hardening, UFW firewall, and deploy user setup
- **templates/**: Jinja2 templates for configuration files
- **files/**: Files like SSH keys or static configs

## How to Run

### Common Role
ansible-playbook -i inventories/dev/hosts.ini playbooks/common.yml

### Nginx Role
ansible-playbook -i inventories/dev/hosts.ini playbooks/nginx.yml

### Security Role
ansible-playbook -i inventories/dev/hosts.ini playbooks/security.yml

## Notes
- Make sure the remote user in ansible.cfg exists and has sudo privileges.
- Public keys for users are in roles/security/files.
- Handlers are used for service restarts.
