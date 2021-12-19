# Docker ready VMs with Vagrant and VirtualBox

## Description

This is a fast way how to run several Docker ready machines on your localhost for tests. It uses a pre-made, public Vagrant box https://app.vagrantup.com/gusztavvargadr/boxes/docker-linux. The config allows Docker VMs to have access to Internet, by using your local network interface in bridge mode and NAT. Hardware specifications can be set per VM. 

## Requirements

- Vagrant
- VirtualBox

## How to use this repo

Create a folder for your Vagrant project. Clone this repo. Run ```vagrant up```.
