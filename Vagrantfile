dkan_ip_address = "192.168.33.237"

Vagrant.configure(2) do |config|
  config.vm.box = "centos7-20170513"
  config.vm.box_url = "https://github.com/sunny4381/vagrant-boxes/releases/download/centos7-20170513/centos7-vagrant-virtualbox-x86_64.box"

  config.vm.define "dkan" do |dkan|
    dkan.vm.network "private_network", ip: dkan_ip_address
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/site.yml"
    ansible.groups = {
      "dkan" => ["dkan"],
    }
    ansible.extra_vars = {
      dkan_ip_address: dkan_ip_address,
    }
  end
end
