# -*- mode: ruby -*-
# vi: set ft=ruby :
# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.
  config.vm.define :desktopX do |config|
    config.vm.hostname = "desktopX"

    # Every Vagrant virtual environment requires a box to build off of.
    config.vm.box = "centos64_7"

    # The url from where the 'config.vm.box' box will be fetched if it
    # doesn't already exist on the user's system.
    config.vm.box_url = "https://f0fff3908f081cb6461b407be80daf97f07ac418.googledrive.com/host/0BwtuV7VyVTSkUG1PM3pCeDJ4dVE/centos7.box"

    # Create a private network, which allows host-only access to the machine
    # using a static IP.
    config.vm.network :private_network, ip: "172.28.128.4", :netmask => "255.255.0.0", adapter: 2
    # Provision x via a shell script
    config.vm.provision "shell", :path => "hello.sh" do |s| "bootstrap.sh"
        s.args = "desktopX"
    end
  end

  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.
  config.vm.define :serverX do |config|
    config.vm.hostname = "serverX"

    # Every Vagrant virtual environment requires a box to build off of.
    config.vm.box = "centos64_7"

    # The url from where the 'config.vm.box' box will be fetched if it
    # doesn't already exist on the user's system.
    config.vm.box_url = "https://f0fff3908f081cb6461b407be80daf97f07ac418.googledrive.com/host/0BwtuV7VyVTSkUG1PM3pCeDJ4dVE/centos7.box"

    # Create a private network, which allows host-only access to the machine
    # using a static IP.
    config.vm.network :private_network, ip: "172.28.128.5", :netmask => "255.255.0.0", adapter: 2
    # Provision x via a shell script
    config.vm.provision "shell", :path => "hello.sh" do |s| "bootstrap.sh"
        s.args = "serverX"
    end
  end

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network :forwarded_port, guest: 80, host: 8080

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network :public_network

  # If true, then any SSH connections made will enable agent forwarding.
  # Default value: false
  # config.ssh.forward_agent = true

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration
  config.vm.provider :virtualbox do |vb|
    # Don't boot with headless mode
    # vb.gui = true
    # Use VBoxManage to customize the VM
    # Increase RAM to 2GB
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end
end
