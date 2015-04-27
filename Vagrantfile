# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "scotch/box"
  config.vm.network "private_network", ip: "192.168.48.48"
  config.vm.hostname = "dairybox"
  config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]

  config.vm.provision "file", source: "bootstrap/bootstrap.sh", destination: "bootstrap.sh"
  config.vm.provision "file", source: "bootstrap/install-apcu.sh", destination: "install-apcu.sh"

  config.vm.provision "bootstrap", type: "shell" do |s|
    s.inline = "sudo ./bootstrap.sh"
  end
end
