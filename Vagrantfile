# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 443, host: 1443

  config.vm.provider "virtualbox" do |v|
    # Display the VirtualBox GUI when booting the machine
    v.gui = false

    # Customize the amount of memory on the VM:
    v.memory = "2048"
    v.cpus   = "2"
  end
  
  config.vm.define "docker01.vagrant.local"
  config.vm.provision "ansible" do |ansible|
    ansible.limit          = "docker01.vagrant.local"
    ansible.playbook       = "dockerswarmrocks-playbook.yml"
    ansible.verbose        = false
    ansible.compatibility_mode = "2.0"
  end
end

