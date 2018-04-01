# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "m300_LB1_db" do |config|
    config.vm.box = "ubuntu/xenial64"
    config.vm.provider "virtualbox" do |config_vb|
      config_vb.name = "m300_LB1_db"
      config_vb.cpus = "1"
      config_vb.memory = "2048"
    end
    config.vm.hostname = "lb1db"
    config.vm.network "private_network", ip: "192.168.10.10"
    config.vm.provision "shell", inline: <<-SHELL
      #SHELL UPDATES
      sudo apt-get update 
      sudo apt-get -y upgrade
      #SHELL INSTALL AND CONFIGURE SERVICES
      sudo systemctl stop ufw
      sudo apt-get install mysql-server
      sudo debconf-set-selections <<< 'mysql-server SQL/root_password password Test123'
      sudo debconf-set-selections <<< 'mysql-server SQL/root_password_again password Test123'
    SHELL

    config.vm.define "m300_LB1_webs" do |config|
      config.vm.box = "ubuntu/xenial64"
      config.vm.provider "virtualbox" do |config_vb|
        config_vb.name = "m300_LB1_webs"
        config_vb.cpus = "1"
        config_vb.memory = "2048"
      end
      config.vm.hostname = "lb1webs"
      config.vm.network "private_network", ip: "192.168.10.100"
      config.vm.network "forwarded_port", guest: 80, host: 1234
      config.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update 
        sudo apt-get -y upgrade
        #SHELL INSTALL AND CONFIGURE SERVICES
        sudo systemctl stop ufw
        sudo apt-get -y install apache2
        sudo systemctl start apache2
        sudo apt-get install php5 libapache2-mod-php5 php5-mysql
        sudo debconf-set-selections <<< 'phpmyadmin phpmyadmin/dbconfig-install boolean true'
        sudo debconf-set-selections <<< 'phpmyadmin phpmyadmin/app-password-confirm password Test123'
        sudo debconf-set-selections <<< 'phpmyadmin phpmyadmin/mysql/admin-pass password Test123'
        sudo debconf-set-selections <<< 'phpmyadmin phpmyadmin/mysql/app-pass password Test123'
        sudo debconf-set-selections <<< 'phpmyadmin phpmyadmin/reconfigure-webserver multiselect apache2'
        sudo debconf-set-selections <<< 'phpmyadmin phpmyadmin/remote/host select 192.168.10.10'
        sudo apt-get -y install phpmyadmin php-mbstring php-gettext
        sudo apt-get -y autoremove phpmyadmin php-mbstring php-gettext
  
      SHELL
    end
  end
end