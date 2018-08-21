# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 80, host: 8081

  config.vm.provider "virtualbox" do |vb|
    vb.name = "tusimple-nginx"
    vb.linked_clone = true
  end

  # Run Ansible from the Vagrant VM
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "nginx.yml"
    ansible.install_mode = "pip"
  end
end
