# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  
  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false  
  end

  config.vm.define 'mysql1' do |machine|
     #machine.vm.box = "ub18LTS"
     machine.vm.box = "centos7"
     #machine.vm.box = "rhel7"
     #machine.vm.box = "generic/rhel7"
  
     machine.vm.hostname = "mysql1.home"
     #machine.vm.synced_folder "/DatabaseMedia/", "/DatabaseMedia"
     #machine.vm.synced_folder "/work/config-genie/", "/config-genie/"
  
     machine.vm.provision :shell, :inline => "sudo rm /etc/localtime && sudo ln -s /usr/share/zoneinfo/Pacific/Auckland /etc/localtime", run: "always"
     machine.vm.provision 'ansible' do |ansible|
      #ansible.playbook = 'playbook.yml'
      ansible.playbook = 'p1.yml'
       ansible.become = true
       ansible.host_key_checking = false
      end
  end
end
