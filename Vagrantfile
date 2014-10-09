# -*- mode: ruby -*-
# vi: set ft=ruby :

NAME = 'angry-hobo'

# See http://docs.vagrantup.com/v2/vagrantfile/version.html
# for explanation of API version
VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.box = 'saucy64'
    config.vm.box_url = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-13.10_chef-provisionerless.box'

    config.berkshelf.berksfile_path = './Berksfile'
    config.omnibus.chef_version = :latest

    config.vm.provider :virtualbox do |vb|
        vb.name = NAME
    end

    config.vm.network :private_network, ip: '192.168.123.123'

    config.vm.hostname = "#{NAME}.local"

    config.vm.synced_folder(
        '.',
        "/home/vagrant/workspace/#{NAME}",
        :owner => 'vagrant',
        :mount_options => ['dmode=775']
    )

    config.vm.provision :chef_solo do |chef|
        chef.custom_config_path = 'ssl_fix.chef'

        chef.run_list = [
            'nodejs',
            'mongodb',
            'angry-hobo::npm_installation'
        ]

        chef.json = {
            :project => {
                :name => NAME
            },
            :nodejs => {
                :install_method => 'package',
                :version => '0.10.28',
                :npm => '1.4.13'
            }
        }
    end
end
