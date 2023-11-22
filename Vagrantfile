Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.provider :libvirt do |libvirt|
    libvirt.cpus = 2
    libvirt.memory = 4096
    libvirt.machine_virtual_size = 25
    libvirt.uri = "qemu:///system"
    libvirt.autostart = true
    libvirt.nested = true
  end
  config.vm.network "forwarded_port", guest: 8182, host: 8182
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yaml"
  end
end
