# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise64"
  config.vm.box_url = 'http://files.vagrantup.com/precise64.box'

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  # config.vm.box_url = "http://domain.com/path/to/above.box"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network :forwarded_port, guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network :private_network, ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network :public_network

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"
  # For lucky people use nfs
  config.vm.synced_folder ".", "/vagrant", :extra => 'dmode=777,fmode=777'

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
 
  config.vm.provider :virtualbox do |vb|
  
    # Use VBoxManage to customize the VM. For example to change memory:
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end
  
  # View the documentation for the provider you're using for more
  # information on available options.


  # Enable provisioning with chef solo, specifying a cookbooks path, roles
  # path, and data_bags path (all relative to this Vagrantfile), and adding
  # some recipes and/or roles.
  #
  config.vm.provision :chef_solo do |chef|
    # Specify vagrant cookbooks: our project cookbooks and magento required cookbooks
    chef.cookbooks_path = ["./myrecipes/cookbooks", "./recipes/cookbooks",]
    #chef.roles_path = "./recipes/roles"
    #chef.data_bags_path = "./recipes/data_bags"
    chef.add_recipe "vagrant_magento"

    # You may also specify custom JSON attributes:
    chef.json = { 
        'vagrant_magento' => {
            'config' => {
                'install' => true,
            },
            'source' => {
                'version' => 'magento-1.8.0.0-alpha1',
            },
            'sample_data' => {
                'install' => false,
                'version' => '1.6.1.0',
            },
        },
    }
    chef.log_level = :debug

    # Add specific configurations for Magento Version
    
  end

end
