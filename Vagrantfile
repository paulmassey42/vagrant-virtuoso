# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  if Vagrant.has_plugin?("vagrant-cachier")
    # Configure cached packages to be shared between instances of the same base box.
    # More info on http://fgrehm.viewdocs.io/vagrant-cachier/usage
    config.cache.scope = :box
    config.cache.enable :apt
  end

  
  config.vm.define "virtuoso" do |virtuoso|
    virtuoso.vm.box = "paulmassey/bionic64-ansible"
    virtuoso.vm.hostname = "virtuoso-docker"    
    virtuoso.vm.synced_folder ".", "/vagrant", owner: "vagrant", group: "vagrant"
    virtuoso.vm.network "forwarded_port", guest: 8080, host: 8080
    virtuoso.vm.network :private_network, ip: "10.0.0.11"
    virtuoso.vm.provider "virtualbox" do |vb2|
      vb2.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      vb2.customize ["modifyvm", :id, "--memory", "8218"]
      vb2.customize ["modifyvm", :id, "--vram", "128"]      
      vb2.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
      vb2.customize ["modifyvm", :id, "--draganddrop", "bidirectional"]
      vb2.gui = true
    end
    
    virtuoso.vm.provision "ansible_local" do |ansible2|
      ansible2.playbook = "playbook.yml"
      # ansible2.verbose = "-vvv"
      # ansible2.vault_password_file = "vault_pass"
    end
  end
end
