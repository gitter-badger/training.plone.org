# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
    config.vm.box = "fedora-23-cloud"
    config.vm.box_url = "http://fedora.inode.at/releases/23/Cloud/x86_64/Images/Fedora-Cloud-Base-Vagrant-23-20151030.x86_64.vagrant-virtualbox.box"

    config.vm.network "private_network", ip: "192.168.60.10"
    config.vm.network "forwarded_port", guest: 80, host: 8080
    config.vm.hostname = "training"

    #config.vm.synced_folder "planet/", "/srv/venus/planet.plone.org"

    config.vm.provider "virtualbox" do |vb|
        vb.customize ["modifyvm", :id, "--ioapic", "on"  ]
        vb.customize ["modifyvm", :id, "--cpus"  , "2"   ]
        vb.customize ["modifyvm", :id, "--memory", "1024"]
        vb.customize ["modifyvm", :id, "--name", "training" ]
    end

    config.vm.provision "shell", path: "scripts/setup.sh"
    end
