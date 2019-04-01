Vagrant.configure("2") do |config|

  config.vm.define "masters1" do |master_node|
    master_node.vm.box = "sbeliakou/centos"
    master_node.vm.hostname = "master1"
    master_node.vm.network "private_network", ip: "192.168.56.15"
    master_node.vm.provider "virtualbox" do |vb|
      vb.name = "master1"
      vb.memory = 2048
    end
  end

  config.vm.define "workers1" do |worker_node|
    worker_node.vm.box = "sbeliakou/centos"
    worker_node.vm.hostname = "worker1"
    worker_node.vm.network "private_network", ip: "192.168.56.16"
    worker_node.vm.provider "virtualbox" do |vb|
      vb.name = "worker1"
      vb.memory = 1048
    end
  end
config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "inventory"
  end
end
