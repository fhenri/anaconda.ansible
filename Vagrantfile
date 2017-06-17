# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/ubuntu1604"
  #config.vbguest.auto_update = false

  config.vm.synced_folder "notebooks/", "/home/vagrant/notebooks"
  config.vm.network "private_network", ip: "192.168.33.12"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provision/playbook.yml"
    ansible.install_mode = "default"
    #ansible.version = "latest"
    ansible.verbose = "true"
    ansible.galaxy_role_file = "provision/requirements.yml"
    ansible.raw_arguments = ["--module-path", "/vagrant/provision/library/ansible-conda"]
  end

end
