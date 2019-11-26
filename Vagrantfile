Vagrant.configure("2") do |config|
  config.vm.box = "debian/contrib-buster64"

  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
  config.vm.synced_folder "src", "/project", type: "virtualbox", owner: "www-data", group: "www-data"

  config.vm.network "forwarded_port", guest: 80, host: 8008

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.compatibility_mode = "2.0"
  end

end
