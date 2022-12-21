# -*- mode: ruby -*-
# vi: set ft=ruby :

$script_servidor1 = <<-EOF
sudo apt update
sudo apt install nginx -y
EOF

Vagrant.configure("2") do |config|
  config.vm.define "servidor1" do |servidor1|
    servidor1.vm.box = "ubuntu/focal64"
    servidor1.vm.network "forwarded_port", guest: 80, host: 8080
    servidor1.vm.network "public_network", ip: "192.168.15.5", bridge: "wlp5s0"
    servidor1.vm.provision "shell", inline: $script_servidor1
    servidor1.vm.synced_folder "site/", "/var/www/html"    
  end
  config.vm.define "servidor2" do |servidor2|
    servidor2.vm.box = "ubuntu/bionic64"
    servidor2.vm.network "forwarded_port", guest: 80, host: 8090
    servidor2.vm.network "public_network", ip: "192.168.15.6", bridge: "enp4s0"
    servidor2.vm.provision "shell", inline: "sudo apt update && sudo apt install apache2 -y"
    servidor2.vm.provision "file", source: "~/.gitconfig", destination: ".gitconfig"
  end
  config.vm.define "servidor3" do |servidor3|
    servidor3.vm.box = "centos/7"
    servidor3.vm.network "forwarded_port", guest: 80, host: 8095
    servidor3.vm.network "private_network", ip: "192.168.56.5"
    servidor3.vm.provision "shell", path: "script.sh"
  end
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
    vb.cpus = 1
  end
end
