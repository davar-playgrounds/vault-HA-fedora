## Introduction

This demo uses [Ansible](https://www.ansible.com) to create [Vault](https://www.vaultproject.io) cluster using [Consul](https://www.consul.io) cluster as HA capable backend. Clusters are deployed on the three [cloud FC23 boxes](https://getfedora.org/en/cloud/download) hosted on [Vagrant](https://www.vagrantup.com) managed VMs. In addition, [Apache HTTPD](https://httpd.apache.org) with [PHP](https://secure.php.net) beside Consul client are installed on the fourth Vagrant VM serving a demo web page in order to demonstrate usage of Vault ("userpass" authentication used). A proper security assessment would need to be done for production deployment and required tasks accomplished accordingly (SSL all accross with cert verification, segragation of public and private networks, firewall/iptables etc.).

![alt tag](vault-HA-fedora.png) 

## Instructions

### Prepare the FC23 host

- Install required software (as root) with: `dnf -y install vagrant-libvirt ansible`
- Add your user account to libvirt unix group (/etc/group)
- Add FC23 cloud box for libvirt (use your own account): `vagrant box add https://download.fedoraproject.org/pub/fedora/linux/releases/23/Cloud/x86_64/Images/Fedora-Cloud-Base-Vagrant-23-20151030.x86_64.vagrant-libvirt.box --name fedora-23`

### Run the demo

- Within the folder where Vagrantfile and demo.yml are located execute: `vagrant up`
- Upon successfull Ansible play run a web browser on the host hosting Vagrant VMs and access the demo web page on: http://192.168.100.104/secret.php. Follow the instructions (username and password are set in the vars section of the client role).
