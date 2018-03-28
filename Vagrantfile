# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "bento/ubuntu-16.04"
  config.ssh.forward_agent = true

  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true

  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 1
    v.customize ["modifyvm", :id, "--cableconnected1", "on"]
  end

  config.vm.define "pipenvtest", primary: true do |pipenvtest|
    pipenvtest.vm.network :private_network, ip: "10.18.3.28"
    pipenvtest.vm.synced_folder ".", "/vagrant", :nfs => true
  end
end
