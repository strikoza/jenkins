# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "jenkins" do |config|
	config.vm.box = "ubuntu/xenial64"
	config.vm.network "private_network", ip: "193.169.2.167"
	config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
  end
	config.vm.provision "shell", inline: <<-SHELL
#	sudo apt-get update
	sudo apt-get install -y git
        sudo add-apt-repository -y ppa:webupd8team/java
        sudo apt update
# 1       sudo apt install -y oracle-java8-installer
        cd /tmp && wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
        echo 'deb https://pkg.jenkins.io/debian-stable binary/' | sudo tee -a /etc/apt/sources.list.d/jenkins.list
        sudo apt update
# 2       sudo apt-get install -y jenkins

# sudo cat /var/lib/jenkins/secrets/initialAdminPassword

	SHELL
  end

end
