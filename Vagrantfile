# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "http://web.sfc.keio.ac.jp/~sasamoto/boxes/rails-env.box"

  config.vm.define :sv1 do |sv|
    sv.vm.hostname = "dev.smafle"
    sv.vm.network :private_network, ip: "192.168.33.30"
    sv.vm.provider :virtualbox do |vb|
      vb.name = "def.smafle"
      vb.memory = 1024
    end
  end

end
