# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "scotch/box"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.hostname = "scotchbox"
  config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"] 
  config.vm.provision "ansible"	do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.sudo = true
    ansible.sudo_user = 'vagrant'
  end
end
