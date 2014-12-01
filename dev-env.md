# Development Environment
I am setting up Vagrant Ubuntu Precise box for Django stuff
Thought I would take notes

### Install Vagrant on host
TODO


### Vagrant
Download  the vagrant file, and place in your apps dir.
`curl -O https://raw.githubusercontent.com/adlawson/vagrantfiles/master/python/Vagrantfile`
`vagrant up`
`vagrant ssh`

#### Inside Vagrant
`sudo apt-get update`
`sudo apt-get install python-dev python-setuptools`

Install pip:
`sudo easy_install pip`

#### Ansible

###### Install
Install Ansible requirements:
`sudo pip install paramiko PyYAML jinja2 httplib2`

`git clone https://github.com/ansible/ansible.git`
`sudo mv ansible /opt && cd $_`
`source ./hacking/env-setup`

`echo "127.0.0.1" > ~/ansible_hosts`
`export ANSIBLE_HOSTS=~/ansible_hosts`

OR install with PIP `sudo pip install ansible` OR...

###### apt-get

Alternatively you may install with APT:
```
$ sudo apt-get install software-properties-common
$ sudo apt-add-repository ppa:ansible/ansible
$ sudo apt-get update
$ sudo apt-get install ansible
```
----------------------------------------------------------------------

###### Ansible - Misc
I had to add the line:
`ssh_args = -o StrictHostKeyChecking=no`
to my `/etc/ansible/ansible.conf`
to allow ssh connection to localhost:2222 without yelling at me about
MITM attack. lol


