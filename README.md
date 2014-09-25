SaltStack Example
==================

This GitHub repository provides several different examples for the configuration
and typical usage of the configuration management software 'salt' by SaltStack.

The SaltStack team provides a walkthrough here: http://docs.saltstack.com/en/latest/topics/tutorials/walkthrough.html

This example focuses on a more practical hands on approach. Using Vagrant and
the provided Vagrantfile, you can quickly get start learning about salt.
Currently the Vagrantfile in this repository will set up three systems (master,
client1, client2) with salt. The vagrantfile will also configure virtualbox to
sync the folders in this repository to the master.

### Requirements

- Vagrant, https://www.vagrantup.com/

### Instructions

To initialize the example:

- Clone to local disk. `git clone https://github.com/666jfox777/vagrant-saltstack-example.git`
- Browse to folder. `cd ~/vagrant-saltstack-example/
- `vagrant up`

Connect to the systems:

- `vagrant ssh master`
- `vagrant ssh client1`
- `vagrant ssh client2`

To remove the example:

- `vagrant destroy`
- `rm -rf ~/vagrant-saltstack-example/`

### Tutorial (Sort of)

TODO

### Disclaimer

I use a lot of saltstack formula's I've written myself in this demo repository. You don't have to.