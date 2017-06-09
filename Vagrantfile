# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vbguest.auto_update = false

  config.vm.network "private_network", ip: "192.168.33.12"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.install_mode = "pip"
    ansible.version = "2.2.1.0"
    ansible.verbose = "true"
    ansible.galaxy_role_file = "requirements.yml"
  end

#  config.vm.provision "ansible" do |ansible|
#    ansible.playbook = "playbook.yml"
#    #ansible.galaxy_role_file = "requirements.yml"
#  end

end
