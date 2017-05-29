Vagrant.configure(2) do |config|
  config.vm.box = "centos7-20170513"
  config.vm.box_url = "https://github.com/sunny4381/vagrant-boxes/releases/download/centos7-20170513/centos7-vagrant-virtualbox-x86_64.box"

  config.vm.network "private_network", ip: '192.168.33.244'
  config.vm.network :forwarded_port, guest: 8244, host: 8244

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/main.yml"
  end
end
