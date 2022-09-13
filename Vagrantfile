Vagrant.configure("2") do |config|
    config.vm.box = "hashicorp/bionic64"
  
    config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 2
    end
  
    #1
    config.vm.define "proxy" do |proxy|
      proxy.vm.hostname = "proxy.test.kikitux.net"
      proxy.vm.network "private_network", ip: "192.168.56.10"
      proxy.vm.provision "shell", path: "scripts/proxy.sh"
    end
  
    #2
    config.vm.define "client" do |client|
      client.vm.hostname = "client.test.kikitux.net"
      client.vm.network "private_network", ip: "192.168.56.9"
      client.vm.provision "shell", path: "scripts/client.sh"
    end
    
  end
  