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

First up is a bit of an explanation about what Salt is, and why it's so awesome.
Salt was originally designed for high-speed communication (aka remote execution)
with large numbers of systems. It then took the next logical step and became a
configuration management utility founded on the same principle of fast
communication.

So at it's core Salt is a remote execution engine, that establishes a
high-speed, secure and bi-directional communication grid for groups of systems.
Then on top of that, Salt provides an extremely fast, flexible and easy-to-use
configuration management system.

What I love most about Salt is how easy it is to use as a configuration
management tool. The configuration files are written in yaml (you'll see
examples soon) and Salt provides many options for templating with jinja (amongst
other engines). It's relatively simple to look at your files and know exactly
what's going on.

So this sort of tutorial is going to cover a few key concepts:

- Remote Execution
- Basic Configuration Management
- Better Configuration Management
- Advanced Configuration Management

All of the steps included in this tutorial should be executed on the included
'master' server. Aka, `vagrant ssh master`.

#### Remote Execution

TODO

#### Basic Configuration Management

TODO

#### Better Configuration Management

TODO

#### Advanced Configuration Management

TODO

### Disclaimer

I use a lot of saltstack formula's I've written myself in this demo repository. You don't have to.