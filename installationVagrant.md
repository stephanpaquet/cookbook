# Comment installer Vagrant

## Prérequis
### VirtualBox

https://www.virtualbox.org/wiki/Linux_Downloads

http://download.virtualbox.org/virtualbox/5.0.16/virtualbox-5.0_5.0.16-105871~Ubuntu~trusty_amd64.deb

sudo dpkg -i virtualbox-5.0_5.0.16-105871-Ubuntu-trusty_amd64.deb


### Installation de Vagrant

https://www.vagrantup.com/downloads.html

Copier le lien vers la distribution Ubuntu 64 bit
https://releases.hashicorp.com/vagrant/1.8.1/vagrant_1.8.1_x86_64.deb

wget -c https://releases.hashicorp.com/vagrant/1.8.1/vagrant_1.8.1_x86_64.deb

sudo dpkg -i vagrant_1.8.1_x86_64.deb

$ Desktop vagrant -v
Vagrant 1.8.1

$ vagrant init hashicorp/precise64
$ vagrant up

