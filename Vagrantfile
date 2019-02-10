require File.dirname(__FILE__)+"/vagrant/dependency_manager"

check_plugins ["vagrant-disksize"]

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/bionic64"
  config.disksize.size = "19GB"
  config.vm.network "private_network", ip: "192.168.69.10"

  config.vm.provider :virtualbox do |vb|
    vb.memory = 876
    vb.cpus = 1
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
  end
end
