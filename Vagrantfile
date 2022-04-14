# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Box settings
  ###################################################################
  # Use box ubuntu/trusty64, it is Official Ubuntu Server 14.04 LTS build
  config.vm.box = "ubuntu/trusty64"

  # Provider settings
  ###################################################################
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 2048 # Give the machine 2 GB of RAM
    vb.cpus = 1 # Give the machine 1 cpu core
  end

  # Network settings, how does the host computer see the quest computer?
  ###################################################################
  # If we access port 8080, forward it to guest 80
  # So basically vagrant up and 127.0.0.1:8080 takes you to the apache server
  config.vm.network "forwarded_port", guest: 80, host: 8080


  # Folder Settings
  ###################################################################
  # Sync the current working directory to vagrants home folder
  config.vm.synced_folder ".", "/home/vagrant/"

  # Provision settings
  ###################################################################
  # Tell vagrant to update the system, install git and apache2
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get upgrade
  #   apt-get install git
  #   apt-get install -y apache2
  # SHELL

  # Instead of the example above, use boostrap.sh to provision
  config.vm.provision "shell", path: "bootstrap.sh"

end
