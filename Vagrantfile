# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vbguest.auto_update = false
  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", 512]
    v.customize ["modifyvm", :id, "--cpus", 1]
  end
  config.vm.box = "debian/stretch64"
  config.vm.hostname = "test-host"
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "tests/test.yml"
    ansible.limit = "all"
    ansible.groups = {
      "test" => ["test-host"]
    }
    ansible.verbose = "-v"
  end
end
