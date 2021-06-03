Vagrant.configure("2") do |config|
    config.vm.box = "debian/bullseye64"
    config.vm.define 'debian'

    # Prevent SharedFoldersEnableSymlinksCreate errors
    config.vm.synced_folder ".", "/vagrant", disabled: true
    
    # Allocate more resources
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "3072"
	    vb.cpus = 2
        vb.customize ['modifyvm', :id, '--nested-hw-virt', 'on']
    end
	
    config.vm.provision "shell", inline: <<-SHELL
	## Setup necessary tools
	apt update
	apt install -y git debos bmap-tools f2fs-tools
	apt-get install -y --no-install-recommends qemu-system libvirt-clients libvirt-daemon-system
	sudo adduser vagrant libvirt
	sudo adduser vagrant kvm
    SHELL
end
