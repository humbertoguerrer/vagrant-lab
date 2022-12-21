# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "servidor1" do |servidor1|
    servidor1.vm.box = "ubuntu/focal64"
  end
  config.vm.define "servidor2" do |servidor2|
    servidor2.vm.box = "centos/7"
  end
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
    vb.cpus = 2
  end
end
