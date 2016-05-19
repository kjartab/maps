Vagrant.configure(2) do |config|


    config.vm.box = "ubuntu/trusty64"
    config.ssh.insert_key = false

    config.vm.provider "virtualbox" do |v|
      v.memory = 4000
      v.cpus = 4
    end

    config.vm.network :forwarded_port, host: 8044, guest: 80 # Apache
    config.vm.network :forwarded_port, host: 8045, guest: 8080 # ElasticSearch

    
    config.vm.provision "ansible" do |ansible| 
        ansible.playbook = "provision/playbook.yml"
    end
end

