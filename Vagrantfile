# -*- mode: ruby -*-
# vi: set ft=ruby :
#
# Vagrant 
# Works from Windows host with Oracle VirtualBox as the provider.


Vagrant.configure("2") do |config|

  # Base box: Ubuntu 22.04 LTS (Jammy)
  config.vm.box = "ubuntu/jammy64"

  config.vm.hostname = "lemp-vagrant"

  # Static private network IP - reachable from Windows host browser
  config.vm.network "private_network", ip: "192.168.56.10"

  # Optional: also forward port 80 to localhost:8080 in case you prefer
  # http://localhost:8080 instead of the private IP
  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true

  # Sync this project folder into the VM (disabled by default to keep VM lean;
  # enable if you want to edit files from Windows and see them in the VM)
  # config.vm.synced_folder ".", "/vagrant"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "vagrant"
    vb.memory = 2048
    vb.cpus = 2
  end

end
