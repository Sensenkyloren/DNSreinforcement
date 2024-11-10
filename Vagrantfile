# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Configuración de la red
  #config.vm.network "private_network", type: "dhcp"

  # Máquina DNSA
  config.vm.define "DNSA" do |dns_a|
    dns_a.vm.box = "debian/bookworm64"  
    dns_a.vm.hostname = "DNSA"
    dns_a.vm.network "private_network", ip: "192.168.57.10"
    dns_a.vm.provision "shell", inline: <<-SHELL
      apt-get update
      sudo ufw allow bind9
      apt-get install -y bind9
      cp -r /vagrant/master/zonas /etc/bind/zonas
      cp -r /vagrant/master/named.conf.local /etc/bind/named.conf.local
    SHELL
  end

  # Máquina DNSB
  config.vm.define "DNSB" do |dns_b|
    dns_b.vm.box = "debian/bookworm64"  
    dns_b.vm.hostname = "DNSB"
    dns_b.vm.network "private_network", ip: "192.168.57.100"
    dns_b.vm.provision "shell", inline: <<-SHELL
      apt-get update
      sudo ufw allow bind9
      apt-get install -y bind9
      cp -r /vagrant/named.conf.local /etc/bind/named.conf.local
    SHELL
  end
#Cliente de ejemplo (IGNORAR)
  config.vm.define "pcprofesor" do |cliente|
    cliente.vm.box = "debian/bookworm64"
    cliente.vm.hostname = "pcprofesor"
    cliente.vm.network "private_network", ip: "192.168.57.20"
    cliente.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y iputils-ping
    SHELL
  end
end