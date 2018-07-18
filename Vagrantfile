# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.define "devserver" do |jenkins|
    jenkins.vm.provider :virtualbox do |v|
      v.name = "devserver"
      v.memory = 1024
      v.cpus = 2
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--ioapic", "on"]
    end
    config.vm.hostname = "devserver"
    jenkins.vm.network :private_network, ip: "192.168.1.10"
  end

  config.vm.provision "shell" do |s|
    s.inline = "apt-get update"
    s.inline = "apt-get install -y python-simplejson"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/site.yml"
    #ansible.verbose = "vvv"
  end
end
