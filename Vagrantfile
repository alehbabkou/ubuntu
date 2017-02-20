# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/trusty64"

    config.vm.define :"ubuntu" do |server|
        server.vm.network :private_network, ip: "172.20.30.11"
        server.vm.network "forwarded_port", guest: 80, host: 4321
        server.vm.provider :virtualbox do |v|
            v.name = "ubuntu"
            v.memory = "3823"
        end
    end

    config.vm.provision :ansible do |ansible|
        ansible.playbook = "provision/main.yml"
#        ansible.inventory_file = "provision/hosts"
        ansible.sudo = true
    end

end
