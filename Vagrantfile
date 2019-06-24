# -*- mode: ruby -*-
# vi: set ft=ruby :
# A Vagrantfile to setup 3 gluster server (skeltal) and one gluster client
file1 = '/home/pi/gluster_store/large_disk1.vdi'
file2 = '/home/pi/gluster_store/large_disk2.vdi'
file3 = '/home/pi/gluster_store/large_disk3.vdi'
Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.define "gluster1" do |vm1|
  	vm1.vm.hostname = "gluster1"
  	vm1.vm.network "private_network", ip: "10.10.1.10"
   	vm1.vm.provider "virtualbox" do |vb|
     		vb.name = "gluster1"
     		vb.gui = false
#                vb.customize ['createhd', '--filename', file1, '--size', 20 * 1024]
                vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', file1]
     		vb.cpus = 2
     		vb.memory = "2048"
   	end
  end
  config.vm.define "gluster2" do |vm2|
  	vm2.vm.hostname = "gluster2"
  	vm2.vm.network "private_network", ip: "10.10.1.20"
   	vm2.vm.provider "virtualbox" do |vb|
     		vb.name = "gluster2"
#                vb.customize ['createhd', '--filename', file2, '--size', 20 * 1024]
                vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', file2]
     		vb.gui = false
     		vb.cpus = 2
     		vb.memory = "2048"
   	end
  end
  config.vm.define "gluster3" do |vm3|
  	vm3.vm.hostname = "gluster3"
  	vm3.vm.network "private_network", ip: "10.10.1.30"
   	vm3.vm.provider "virtualbox" do |vb|
     		vb.name = "gluster3"
#                vb.customize ['createhd', '--filename', file3, '--size', 20 * 1024]
                vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', file3]
     		vb.gui = false
     		vb.cpus = 2
     		vb.memory = "2048"
   	end
  end
  config.vm.define "client" do |vm4|
  	vm4.vm.hostname = "client"
  	vm4.vm.network "private_network", ip: "10.10.1.40"
   	vm4.vm.provider "virtualbox" do |vb|
     		vb.name = "client"
     		vb.gui = false
     		vb.cpus = 2
     		vb.memory = "2048"
   	end
  end
end
