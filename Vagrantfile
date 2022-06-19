# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.define "ubuntu_192.168.33.111"
  config.vm.network "private_network", ip: "192.168.33.111"
  config.vm.hostname = "python"

  config.vm.provider "libvirt" do |kvm|
    kvm.memory = 4096 
    kvm.cpus = 2
    kvm.storage_pool_name = "data"
    kvm.machine_type = "q35"
  end

  config.vm.provision "shell", inline: <<-SHELL
     apt-get update
     apt-get install -y openssh-server
   SHELL
end
