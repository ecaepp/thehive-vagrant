# -*- mode: ruby -*-
# vi: set ft=ruby :


# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

require 'yaml'


vagrant_config = YAML.load_file("config.yaml")


Vagrant.configure("2") do |config|
  #config.vm.box = "ubuntu/xenial64"
  vagrant_config.each do |servers|
    config.vm.define servers['hostname'] do |node|
      node.vm.box = servers['box']
      node.vm.hostname = servers['hostname']
      node.vm.network :private_network, ip: servers['private_ip']

      # This loop is to be able to add multiple forwarded ports using an array in `config.yaml`
      servers['guest'].zip(servers['host']).each do |g, h|
        "node.vm.network :forwarded_port, guest: #{g}, host: #{h},"
      end # end for each loop

      node.vm.provision "ansible" do |ansible|
        ansible.playbook = servers['playbook']
      end # end for provision

      node.vm.provider servers['provider'] do |setup|
        setup.name = servers['name']
        setup.memory = servers['ram']
      end
    end
  end
end