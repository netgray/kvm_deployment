# kvm_deployment

Ansible playbook installs KVM to Ubuntu, download and install Whonix (Gateway and Workstation) with default configuration.

Ubuntu server must have two network interfaces:
- Internet
- Local

1. Create user with sudo permissions on the server.
2. Copy public SSH key to Ubuntu server:
https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04
3. Install and configure Ansible on control node:
https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-20-04
4. Copy files (inventory, playbook.yml) to control node
5. Change
- username in playbook.yml
- Ubunty server IP in "inventory"
6. Execute command on control node:
- to check connection to Ubuntu server:
ansible all -i inventory -m ping
- to run palybook:
ansible-playbook -i inventory playbook.yml  -K

After "BECOME password" - enter user password (for sudo command)

When Whonix installed - you can use virt-manager to finish Whonix configuration.