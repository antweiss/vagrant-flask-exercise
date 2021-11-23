# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|





 #box settings
 
  config.vm.box = "ubuntu/focal64"







 
  #providor settings
  
  config.vm.provider "virtualbox" do |vb|

    vb.memory = 2048
    vb.cpus = 4  
    end





 
 
 
 
 #network settings
 
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.network "forwarded_port", guest: 5000, host: 5000


  # config.vm.network "private_network", ip: :127.0.0.1:5000"

 
  # config.vm.network "public_network"


  # config.vm.synced_folder "../data", "/vagrant_data"


 



#provision settings

config.vm.provision "shell", inline: <<-SHELL
  
  sudo apt-get update
  
  sudo apt install curl -y
  
 curl -LJO https://raw.githubusercontent.com/georgef21/vagrant-flask-exercise/main/deployment
  
  chmod +x deployment
  
  ./deployment
  
 
 SHELL
end






