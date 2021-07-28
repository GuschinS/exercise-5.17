# set up the default terminal
ENV["TERM"]="linux"

Vagrant.configure("2") do |config|
  
  # set the image for the vagrant box
  config.vm.box = "opensuse/Leap-15.2.x86_64"
  ## Set the image version
  # config.vm.box_version = "15.2.31.212"

  # st the static IP for the vagrant box
  config.vm.network "private_network", ip: "192.168.50.4"
  # config.vm.network "forwarded_port", guest: 6111, host: 6111, host_ip: "127.0.0.1"
  config.vm.network "forwarded_port", guest: 6112, host: 6112, host_ip: "127.0.0.1"
  
  # consifure the parameters for VirtualBox provider
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
    vb.cpus = 4
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
  end
end
