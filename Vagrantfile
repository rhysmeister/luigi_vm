Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  # Add 4GB RAM
  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--name", "luigi",
      "--memory", "4096"
    ]
  end

  config.vm.hostname = "luigi"
  config.vm.network "private_network", ip: "192.168.4.111"
  config.vm.network "forwarded_port", guest: 8082, host: 8082

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "luigi.yml"
  end

end
