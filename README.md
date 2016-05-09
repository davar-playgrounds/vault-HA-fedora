# vault-HA-fedora
### Introduction

This demo uses Ansible to create Vault cluster using Consul cluster as HA capable backend. Clusters are deployed on the three cloud FC23 boxes hosted on Vagrant VMs. In addition, Apache HTTPD with PHP beside Consul client are installed on the fourth Vagrant VM serving a demo web page in order to demonstrate usage of Vault ("userpass" authentication used) .

### Instructions

## Prepare the FC23 host

- Install required software (as root) with: `dnf -y install vagrant-libvirt ansible`
- Add your user account to libvirt group
- 

## Run the demo

- within the folder where Vagrantfile and demo.yml located execute: `vagrant up`
- access the demo web page upon successfull Ansible play on: http://192.168.100.104/secret.php
