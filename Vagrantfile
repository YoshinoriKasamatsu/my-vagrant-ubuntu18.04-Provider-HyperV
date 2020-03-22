# -*- mode: ruby -*-
# vi: set ft=ruby :

# you're doing.
Vagrant.configure("2") do |config|
  # main
  config.vm.define "main" do |main|
    # Set Image
    main.vm.box = "hashicorp/bionic64"
    main.vm.provider "hyperv" do |vb|
      vb.cpus = 2
      vb.memory = 8192
      vb.enable_virtualization_extensions = true
      vb.linked_clone = true
    end
    main.vm.network "public_network"
    main.vm.synced_folder ".","/vagrant", disabled: true
    main.vm.provision :shell, :path => "./shell/useradd.sh"
    main.vm.provision :shell, :path => "./shell/install_python.sh"
    main.vm.provision :shell, :path => "./shell/install_pip.sh"
    main.vm.provision :shell, :path => "./shell/install_ansible.sh"
    main.vm.provision :shell, :path => "./shell/install_ubuntu_desktop.sh"
    main.vm.provision :shell, :path => "./shell/install_chrome.sh"
    main.vm.provision :shell, :path => "./shell/install_nodejs.sh"
    main.vm.provision :shell, :path => "./shell/install_vscode.sh"
  end
end
