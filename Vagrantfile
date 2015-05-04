# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision :shell, :path => "bootstrap.sh", privileged: false
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.ssh.forward_agent = true

  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
    # vb.cpus = 2
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end
end
