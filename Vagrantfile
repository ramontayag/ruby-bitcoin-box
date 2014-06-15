# -*- mode: ruby -*-
# vi: set ft=ruby :
require "yaml"

CONFIG = YAML.load_file("config.yml")

VM_BOX="ruby-bitcoin-box"
VM_BOX_URL="https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
VM_IP_ADDRESS=CONFIG["ip"]
VM_MEMORY=CONFIG["memory"]
VM_CPU=CONFIG["cpu"]

Vagrant.configure("2") do |config|
  config.vm.box = VM_BOX
  config.vm.box_url = VM_BOX_URL
  config.vm.network :private_network, ip: VM_IP_ADDRESS
  config.ssh.forward_agent = true
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--memory", VM_MEMORY]
    v.customize ["modifyvm", :id, "--cpus", VM_CPU]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end
  config.vm.synced_folder "mnt", "/home/vagrant/src", id: "vagrant-src", nfs: true

end
