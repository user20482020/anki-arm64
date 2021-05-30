Vagrant.configure("2") do |config|
    config.vm.box = "debian/bullseye64"

    config.vm.define 'debian'

    # Prevent SharedFoldersEnableSymlinksCreate errors
    config.vm.synced_folder ".", "/vagrant", disabled: true
end
