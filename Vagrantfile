Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.network "private_network", type: "dhcp"
  config.vm.hostname = "demo"

  config.vm.define "demo" do |demo|
  end

  config.vm.provision "shell",
    inline: "yum -y install epel-release && yum repolist && yum -y install ansible xorg-x11-xauth"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "/vagrant/demo-playbook/site.yml"
    ansible.sudo = true
  end

end
