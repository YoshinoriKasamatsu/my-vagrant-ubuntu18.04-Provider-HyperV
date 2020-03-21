# -*- mode: ruby -*-
# vi: set ft=ruby :

# you're doing.
Vagrant.configure("2") do |config|
  # main
  config.vm.define "main" do |main|
    # Set Image
    main.vm.box = "hashicorp/bionic64"
    main.vm.provider "hyperv" do |vb|
      vb.memory = 8192
      #vb.gui = true
    end
    main.vm.synced_folder ".", "/vagrant", type: "smb", mount_options:["smb_username=dev","smb_password=dev"]
    main.vm.provision :shell, :path => "./shell/useradd.sh"
    main.vm.provision :shell, :path => "./shell/install_python.sh"
    main.vm.provision :shell, :path => "./shell/install_pip.sh"
    main.vm.provision :shell, :path => "./shell/install_ansible.sh"
    main.vm.provision :shell, :path => "./shell/install_ubuntu_desktop.sh"
    main.vm.provision :shell, :path => "./shell/install_virtualbox_additions.sh"
    main.vm.provision :shell, :path => "./shell/install_chrome.sh"
    main.vm.provision :shell, :path => "./shell/install_nodejs.sh"
    main.vm.provision :shell, :path => "./shell/install_vscode.sh"
  end
end
