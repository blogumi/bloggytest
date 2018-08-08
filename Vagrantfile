# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.hostname = "tjamcchefdev00"
  # Required for NFS to work, pick any local IP
  config.vm.network :private_network, ip: '192.168.50.50'
  # Use NFS for shared folders for better performance
  config.vm.synced_folder '.', '/vagrant', nfs: true
  config.vm.box = "centos/7"

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
    # Customize the amount of memory on the VM:
    vb.memory = "4096"
    vb.cpus = "4"
  end
  #
  config.omnibus.chef_version = :latest
  config.vm.provision :chef_client do |chef|
    chef.provisioning_path = "/etc/chef"
    chef.chef_server_url = "https://api.chef.io/organizations/amctheatres"
    chef.validation_key_path = "~/chef-repo/.chef/amctheatres-validator.pem"
    chef.validation_client_name = "amctheatres-validator"
    chef.node_name = "tjamcchefdev00"
    chef.add_role "chef-client"
    chef.environment = "development"
    chef.delete_node = true
    chef.delete_client = true
  end
end
