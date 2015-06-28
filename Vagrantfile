# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end

  config.berkshelf.berksfile_path = "./infra/Berksfile"

  config.berkshelf.enabled = true

  config.vm.provision "chef_solo" do |chef|
    chef.cookbooks_path = "./cookbooks"
    chef.run_list = ['railsapp']
  end

end
