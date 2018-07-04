# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    sudo apt update -y
    sudo apt dist-upgrade -y
    sudo apt autoremove -y
    sudo add-apt-repository -y ppa:ethereum/ethereum
    sudo apt-get update -y
    sudo apt-get install ethereum -y
    sudo apt-get install solc -y
    curl -L git.io/nodebrew | perl - setup
    echo 'export PATH=$HOME/.nodebrew/current/bin:$PATH' >> ~/.bashrc
    export PATH=$HOME/.nodebrew/current/bin:$PATH
    nodebrew install-binary v8.7.0
    nodebrew use v8.7.0
  SHELL
end
