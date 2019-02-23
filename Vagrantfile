# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  
  config.vm.provider "virtualbox" do |vb| 
      vb.gui = false
      vb.memory = "2048"
      vb.cpus = 2
  end 

  config.vm.provision "shell",  inline: "swapoff -a"

 # config.vm.provision "file", source: "./pkg", destination: "pkg"
  config.vm.provision "file", source: "./scripts", destination: "scripts"
 
  config.vm.provision "shell",  inline: "/bin/sh ./scripts/install-docker.sh"
  config.vm.provision "shell",  inline: "/bin/sh ./scripts/install-kubeadm.sh"

  # Install Calico
  # kubeadm init --pod-network-cidr=192.168.0.0/16 
  # kubectl apply -f https://docs.projectcalico.org/v3.3/getting-started/kubernetes/installation/hosted/rbac-kdd.yaml  # kubectl apply -f https://docs.projectcalico.org/v3.3/getting-started/kubernetes/installation/hosted/kubernetes-datastore/calico-networking/1.7/calico.yaml
  
end

