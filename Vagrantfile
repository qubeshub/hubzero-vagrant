# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.hostname = "scotchbox"
    config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=777"]
    config.vm.box_version = "2.5"
    
    # Optional NFS, TCP, and async (MUCH faster syncing and performance). Make sure to remove other synced_folder line too.
    # See https://blog.theodo.com/2017/07/speed-vagrant-synced-folders/ for local tweaking.
    # config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666","tcp"] }, linux__nfs_options: ['rw','no_subtree_check','all_squash','async']

    config.vm.provision "shell", path:"provision/setup.sh"
end
