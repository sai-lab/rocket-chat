Vagrant.configure("2") do |config|

  config.vm.box = "generic/ubuntu2004"

  config.vm.provider :libvirt do |libvirt|
    libvirt.driver = "qemu"
  end

  config.vm.synced_folder ".", "/home/vagrant/rocket-chat"
  config.vm.network "forwarded_port", guest: 8888, host: 8888

  config.vm.provider "libvirt" do |v|
    v.cpus = 4
    v.memory = 8192
  end

  config.vm.provision "shell", path: "./provisioning/provisioning.sh"
end
