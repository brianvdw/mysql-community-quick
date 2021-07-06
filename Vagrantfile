# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  
  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false  
  end

  config.vm.define 'mysql1' do |machine|
     #machine.vm.box = "generic/rhel7"
     machine.vm.box = "bento/centos-7"
  
     machine.vm.hostname = "lab1"
  
     machine.vm.provision :shell, :inline => "sudo rm /etc/localtime && sudo ln -s /usr/share/zoneinfo/Pacific/Auckland /etc/localtime", run: "always"
     machine.vm.provision 'ansible' do |ansible|
      #ansible.playbook = 'playbook.yml'
      ansible.playbook = 'ping.yml'
       ansible.become = true
       ansible.host_key_checking = false
      end
  end
end
