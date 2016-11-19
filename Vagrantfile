# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  # Set vagrant box.
  config.vm.box = "puppetlabs/centos-7.2-64-nocm"

  #=============================================================================
  # Provisioning.
  #=============================================================================

  # Yum packages.
  config.vm.provision "shell",
    path: "script/yum.sh",
    privileged: true

  # Configuration files.
  config.vm.provision "shell",
    path: "script/rc.sh",
    privileged: false

  # Miniconda.
  config.vm.provision "shell",
    path: "script/miniconda_install.sh",
    privileged: false

  # Miniconda packages.
  config.vm.provision "shell",
    path: "script/miniconda_packages.sh",
    privileged: false

  # ccache
  config.vm.provision "shell",
    path: "script/ccache.sh",
    privileged: true

  # Memory and CPU.
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

end
