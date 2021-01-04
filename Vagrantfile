Vagrant.configure("2") do |config|
  config.vm.define "serv1", primary: true do |serv1|

    serv1.vm.hostname = "serv1"

    serv1.vm.box = "generic/ubuntu2004"
    serv1.vm.box_version = "3.1.14"

    serv1.vm.network "public_network"
    serv1.vm.network "private_network", ip: "192.168.11.101"

    serv1.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end

    serv1.vm.provision "shell", path: "serv1.sh"

  end

  config.vm.define "serv2" do |serv2|

    serv2.vm.hostname = "serv2"

    serv2.vm.box = "generic/ubuntu2004"
    serv2.vm.box_version = "3.1.14"

    serv2.vm.network "public_network"
    serv2.vm.network "private_network", ip: "192.168.11.102"

    serv2.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end

    serv2.vm.provision "file", source: "./backup.sh", destination: "$HOME/backup.sh"
    serv2.vm.provision "shell", path: "serv2.sh"

  end

end
