# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  ###################
  ##  Base image
  ##############

  # Run with Ubuntu 14.04
  config.vm.box = "ubuntu-14.04"

  # Download URL Ubuntu 14.04
  config.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-14.04_chef-provisionerless.box"

  ###################
  ## Network configuration
  ##############

  config.vm.network "forwarded_port", guest: 3000, host: 3000

  ###################
  ## VM system settings
  ##############

  config.vm.provider :virtualbox do |vb|
    # Use VBoxManage to customize the VM. For example to change memory:
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    # vb.gui = true
  end

  ###################
  ## Install Chef client
  ##############

  config.vm.provision :shell do |shell|
    shell.inline = "which chef-client || wget -qO- https://www.opscode.com/chef/install.sh | bash"
  end

  ###################
  ## Provisioning settings
  ##############

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe "frab"
  end
end
