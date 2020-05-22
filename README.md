# ansible-testenv

Vagrant environment with an Ubuntu 20.04 LTS VM for testing Ansible roles using Molecule and Docker.

## Setup

- Fork and/or clone this repository
- Enter the directory
- Edit `vagrant_hosts.yml` and change the `src:` field of the synced folder to the directory on the physical system where Ansible roles are kept.
- Start the environment with `vagrant up`

## Requirements

- [Git](https://git-scm.com/downloads) (including Git Bash on Windows)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (including the Extension Pack!)
- [Vagrant](https://www.vagrantup.com/)

## Usage

### Role testing

Log in on the VM with `vagrant ssh` and enter the role directory with `cd ansible/ROLE_NAME`. From there, you can execute `molecule test` (provided Molecule testing was initialized for that role).

### Monitoring

The VM has some tools for monitoring the system and manage containers.

- [Cockpit](https://cockpit-project.org/) (web based system monitoring dashboard): <https://192.168.56.20:9090>
    - Log in with user `vagrant` and password `vagrant`
- [Portainer.io](https://portainer.io) (webinterface for Docker management): <https://192.168.56.200:9000>
    - The first time you access the Portainer webinterface, you need to create an admin user account.
    - Portainer is installed as a Docker container. It should start automatically after system boot & any configuration you change should be persistent.


