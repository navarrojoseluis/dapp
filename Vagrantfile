Vagrant.configure("2") do |config|  
    config.vm.define :truffle, primary:true, autostart:true do |truffle|
      truffle.vm.box = "bento/ubuntu-18.04"
      truffle.vm.hostname = "truffle"

      truffle.vm.network "private_network", ip: "10.20.0.2"
  
      truffle.vm.synced_folder "./", "/home/vagrant"
  
      truffle.vm.provider "virtualbox" do |vb|
        vb.gui = false
        vb.name = "truffle"
        vb.memory = "1024"
        vb.cpus = 1
      end
  
      truffle.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "ansible/truffle.yml"
      end
    end   
  end
  