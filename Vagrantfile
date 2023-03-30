Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end
  
  config.vm.define "ansible-master" do |ansible|
    ansible.vm.hostname = "ansible-master"
    ansible.vm.network "private_network", ip: "192.168.33.10"
  end
  
  config.vm.define "ans-node1" do |node1|
    node1.vm.hostname = "ans-node1"
    node1.vm.network "private_network", ip: "192.168.33.101"
  end
  
  config.vm.define "ans-node2" do |node2|
    node2.vm.hostname = "ans-node2"
    node2.vm.network "private_network", ip: "192.168.33.12"
  end
end
