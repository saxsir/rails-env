# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "http://web.sfc.keio.ac.jp/~sasamoto/boxes/rails-env.box"
  # config.vm.box = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"

  config.vm.define :sv1 do |sv|
    sv.vm.hostname = "rails-env"
    sv.vm.network :private_network, ip: "192.168.33.30"
    sv.vm.provider :virtualbox do |vb|
      vb.name = "rails-env"
      vb.memory = 1024
    end
  end

end
