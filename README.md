
# Scripts for creating Virtual Machines

This project will set up the demonstration environment for Stucco using [Packer](http://www.packer.io/) to create [VitualBox](https://www.virtualbox.org/) and [VMware Fusion](http://www.vmware.com/products/fusion/features.html)/[VMware Workstation](http://www.vmware.com/products/workstation/features.html) virtual machines for use with [Vagrant](http://www.vagrantup.com/). 

## Setup

1. [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads) for your OS and install. This was tested with version 4.3.x.
2. [Download Vagrant](http://www.vagrantup.com/downloads.html) for your OS and install. This was tested with version 1.6.x.
3. [Download Ansible](http://docs.ansible.com/intro_installation.html). This was tested with version 1.7.x.
4. [Download Packer](https://www.packer.io/downloads.html) for your OS and install. This was tested with version 0.7.x.
5. Get this repo from [github](https://github.com/stucco/demo): `git clone https://github.com/stucco/demo.git`.
6. Run `packer build stucco.json` to build the VMs and Vagrant box.
7. Add the vagrant box for virtualbox (or vmware): `vagrant box add ./stucco-virtualbox.box --name=stucco/stucco-ubuntu1404`.
8. Run `vagrant up` to start the VM.

## Notes

* If you notice an `ISO download failed` or similar error, it is possible that the base OS image is no longer available.  Check the `iso_url` field(s) in the `stucco.json` config file, and if needed update it and its matching `iso_checksum` field(s).  If you do notice this, please point it out to us.
