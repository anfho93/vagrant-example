# -*- mode: ruby -*-
# vi: set ft=ruby :


NODE_SCRIPT = <<EOF.freeze
echo "Preparing node..."
# ensure the time is up to date
EOF

TI_SCRIPT = <<EOF.freeze
echo "Preparing node..."
# ensure the time is up to date
EOF

def set_hostname(server)
server.vm.provision 'shell', inline: "hostname #{server.vm.hostname}"
end

Vagrant.configure(2) do |config|
# Defines a configuration environment for the webapp locally for testing
    # TI
    config.vm.define 'nodo-ti' do |n|
    n.vm.network "private_network", ip: "192.168.50.2", netmask: "24"
    n.vm.box = 'bento/ubuntu-18.04'
    n.vm.box_version = '202007.17.0'
    n.vm.hostname = 'nodo-ti'
    n.vm.provision :shell, inline: NODE_SCRIPT.dup
    set_hostname(n)
    end

    # REPUESTOS
    config.vm.define 'nodo-repuesto' do |n|
    n.vm.network "private_network", ip: "192.168.51.2", netmask: "24"
    n.vm.box = 'bento/ubuntu-18.04'
    n.vm.box_version = '202007.17.0'
    n.vm.hostname = 'nodo-repuesto'
    n.vm.provision :shell, inline: NODE_SCRIPT.dup
    set_hostname(n)
    end
end
    