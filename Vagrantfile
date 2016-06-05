# -*- mode: ruby -*-
# vi: set ft=ruby :

PROJECT_NAME = "boston"
PROJECT_FOLDER = PROJECT_NAME + "_prj"

Vagrant.configure(2) do |config|
  config.vm.box = "marcoaltieri/ubuntu-desktop-16.04-64bit"
  config.vm.hostname = PROJECT_NAME

  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "1024"
  end

  config.vm.synced_folder ".", "/home/vagrant/" + PROJECT_FOLDER
  config.vm.provision :shell, path: "provision.sh", args: PROJECT_FOLDER

  ENV["LC_ALL"] = "en_US.UTF-8"

  config.vm.network "forwarded_port", guest: 8888, host: 8888
end
