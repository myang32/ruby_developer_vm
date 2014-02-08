Ruby Developer VM
=================

Virtualbox based virtual machine with Ubuntu 13.10 with a complete RubyOnRails/Ruby development environment.
The VM is localised for a german audience.

Login with user "vagrant" and password "vagrant".

The MySQL-Root user is "root". The password is "vagrant".

## Build base box
You can build the base box with the provided packer template.

    cd packer-template
    cd ubuntu_1310
    packer build -only=virtualbox-iso template.json
    vagrant box add ubuntu1310_new ./ubuntu1310.box

## Build developer VM
Afterwards use the Vagrantfile with the base box to install the rest of the VM.

    cd vagrant
    cd ubuntu_1310
    vagrant plugin install vagrant-berkshelf
    bundle
    berks
    vagrant up

Tested with VirtualBox 4.3.6 and VMware Workstation 9.0.2 and Ubuntu 13.10 on Windows 7 Enterprise.
