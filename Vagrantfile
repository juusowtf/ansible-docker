# -*- mode: ruby -*-
# vi: set ft=ruby :

boxes = [ { name: "debian", image: "debian/jessie64", private_ip: "192.168.33.55" } ]

Vagrant.configure(2) do |config|

  boxes.each do |box|
    box_name = "ansible-docker-#{box[:name]}"
    config.vm.define box_name do |env|
      env.vm.box = box[:image]
      env.vm.hostname = box_name

      env.vm.provider :virtualbox do |vb|
        vb.name = box_name
        vb.cpus = 1
        vb.memory = 1024
      end

      env.ssh.insert_key = false
      env.vm.network :private_network, ip: box[:private_ip]
    end
  end

end
