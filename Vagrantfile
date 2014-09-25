# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"


Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "nrel/CentOS-6.5-x86_64"
  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 1
  end

  config.vm.define "master" do |server|
    server.vm.host_name = "master"
    server.vm.network "private_network", ip: "192.168.250.100"
    server.vm.synced_folder "pillar/", "/srv/pillar/"
    server.vm.synced_folder "salt/", "/srv/salt/"
    server.vm.provision "shell", inline: "sudo bash"
    server.vm.provision "shell", inline: "service iptables stop"
    server.vm.provision "shell", inline: "rpm -Uvh http://dl.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm"
    server.vm.provision "shell", inline: "echo '192.168.250.100 salt' >> /etc/hosts"
    server.vm.provision "shell", inline: "yum install git -y"
    server.vm.provision "shell", inline: "yum install salt-master -y"
    server.vm.provision "shell", inline: "chkconfig salt-master on"
    server.vm.provision "shell", inline: "cp -f /vagrant/master /etc/salt/"
    server.vm.provision "shell", inline: "service salt-master start"
    server.vm.provision "shell", inline: "yum install salt-minion -y"
    server.vm.provision "shell", inline: "chkconfig salt-minion on"
    server.vm.provision "shell", inline: "echo 'master' >> /etc/salt/minion_id"
    server.vm.provision "shell", inline: "service salt-minion start"
    server.vm.provision "shell", inline: "crontab -l | fgrep -i -v 'salt-key -A -y' | echo '* * * * * salt-key -A -y' | crontab -"
  end

  config.vm.define "client1" do |server|
    server.vm.host_name = "client1"
    server.vm.network "private_network", ip: "192.168.250.101"
    server.vm.provision "shell", inline: "sudo bash"
    server.vm.provision "shell", inline: "service iptables stop"
    server.vm.provision "shell", inline: "rpm -Uvh http://dl.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm"
    server.vm.provision "shell", inline: "echo '192.168.250.100 salt' >> /etc/hosts"
    server.vm.provision "shell", inline: "yum install salt-minion -y"
    server.vm.provision "shell", inline: "chkconfig salt-minion on"
    server.vm.provision "shell", inline: "echo 'master' >> /etc/salt/minion_id"
    server.vm.provision "shell", inline: "service salt-minion start"
  end

  config.vm.define "client2" do |server|
    server.vm.host_name = "client2"
    server.vm.network "private_network", ip: "192.168.250.102"
    server.vm.provision "shell", inline: "sudo bash"
    server.vm.provision "shell", inline: "service iptables stop"
    server.vm.provision "shell", inline: "rpm -Uvh http://dl.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm"
    server.vm.provision "shell", inline: "echo '192.168.250.100 salt' >> /etc/hosts"
    server.vm.provision "shell", inline: "yum install salt-minion -y"
    server.vm.provision "shell", inline: "chkconfig salt-minion on"
    server.vm.provision "shell", inline: "echo 'master' >> /etc/salt/minion_id"
    server.vm.provision "shell", inline: "service salt-minion start"
  end
end