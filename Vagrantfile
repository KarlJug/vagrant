Vagrant.configure("2") do |config|

config.vm.define "ansible" do |ansible|
  ansible.vm.box = "generic/debian12"
  ansible.vm.network "public_network"
  ansible.vm.network "private_network", ip: "192.168.50.51", virtualbox__intnet: "ansible_lab"
  ansible.vm.hostname = "Ansible-Karl"
  ansible.vm.synced_folder "./ansible_data", "/vagrant_data"
  ansible.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
	vb.name = "Ansible-Karl"
    end
  ansible.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y git ansible
  SHELL
  end
config.vm.define "debian" do |debian|
  debian.vm.box = "generic/debian12"
  debian.vm.network "public_network"
  debian.vm.network "private_network", ip: "192.168.50.52", virtualbox__intnet: "ansible_lab"
  debian.vm.hostname = "Debian-Karl"
  debian.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
	vb.name = "Debian-Karl"
    end
  end
config.vm.define "ubuntu" do |ubuntu|
  ubuntu.vm.box = "generic/ubuntu2304"
  ubuntu.vm.network "public_network"
  ubuntu.vm.network "private_network", ip: "192.168.50.53", virtualbox__intnet: "ansible_lab"
  ubuntu.vm.hostname = "Ubuntu-Karl"
  ubuntu.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
	vb.name = "Ubuntu-Karl"
    end
  end
config.vm.define "alma" do |alma|
  alma.vm.box = "generic/alma9"
  alma.vm.network "public_network"
  alma.vm.network "private_network", ip: "192.168.50.54", virtualbox__intnet: "ansible_lab"
  alma.vm.hostname = "Alma-Karl"
  alma.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
	vb.name = "Alma-Karl"
    end
  end
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y fish mc sshpass python
  SHELL
end