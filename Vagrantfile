# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|

  config.vm.define "gitlab" do |gitlab|
    gitlab.vm.box="webysther/gitlab-ce-ubuntu-x64-14.04"
    gitlab.vm.hostname = "gitlab-server"
    gitlab.vm.network "private_network", ip: "192.168.33.5"
	#gitlab.vm.network "forwarded_port", guest: 22, host: 2225, auto_correct: true
	gitlab.vm.network "forwarded_port", guest: 80, host: 12080, auto_correct: true
	gitlab.vm.network "forwarded_port", guest: 443, host: 12443, auto_correct: true
  end
  
  config.vm.define "chef" do |chef|
	chef.vm.box = "centos-7.2"
	chef.vm.hostname = "chef-server"
	chef.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
	chef.vm.network "forwarded_port", guest: 443, host: 8443, auto_correct: true
	#chef.vm.network "forwarded_port", guest: 22, host: 2210, auto_correct: true
	chef.vm.network "private_network", ip: "192.168.33.10"
  end

  config.vm.define "jenkinsu" do |jenkinsu|
	jenkinsu.vm.box = "jenkins-trusty64"
	jenkinsu.vm.hostname = "jenkinsu-server"
	#jenkinsu.vm.network "forwarded_port", guest: 22, host: 2211, auto_correct: true
	jenkinsu.vm.network "forwarded_port", guest: 8080, host: 11080, auto_correct: true
	jenkinsu.vm.network "private_network", ip: "192.168.33.11"
  end

  config.vm.define "puppet" do |puppet|
	puppet.vm.box = "centos-7.2"
	puppet.vm.hostname = "puppet-server"
	puppet.vm.network "forwarded_port", guest: 80, host: 9080, auto_correct: true
	puppet.vm.network "forwarded_port", guest: 443, host: 9443, auto_correct: true
	#puppet.vm.network "forwarded_port", guest: 22, host: 2215, auto_correct: true
	puppet.vm.network "private_network", ip: "192.168.33.15"
  end
  
  config.vm.define "foreman" do |foreman|
	foreman.vm.box = "centos-7.2"
	foreman.vm.hostname = "foreman-server"
	foreman.vm.network "forwarded_port", guest: 80, host: 14080, auto_correct: true
	foreman.vm.network "forwarded_port", guest: 443, host: 14443, auto_correct: true
	#foreman.vm.network "forwarded_port", guest: 22, host: 2214, auto_correct: true
	foreman.vm.network "private_network", ip: "192.168.33.14"
  end
  
  config.vm.define "docker" do |docker|
	docker.vm.box = "centos-7.2"
	docker.vm.hostname = "docker-server"
	#docker.vm.network "forwarded_port", guest: 22, host: 2216, auto_correct: true
	docker.vm.network "private_network", ip: "192.168.33.16"
  end

  config.vm.define "node1" do |node1|
    node1.vm.box="centos-7.2"
    node1.vm.hostname = "centos-node1"
    node1.vm.network "private_network", ip: "192.168.33.20"
	#node1.vm.network "forwarded_port", guest: 22, host: 2220, auto_correct: true
  end
  
  config.vm.define "node2" do |node2|
    node2.vm.box="centos-7.2"
    node2.vm.hostname = "centos-node2"
    node2.vm.network "private_network", ip: "192.168.33.21"
	#node2.vm.network "forwarded_port", guest: 22, host: 2221, auto_correct: true
  end
  
  config.vm.define "node3" do |node3|
    node3.vm.box="centos-7.2"
    node3.vm.hostname = "centos-node3"
    node3.vm.network "private_network", ip: "192.168.33.22"
	#node3.vm.network "forwarded_port", guest: 22, host: 2222, auto_correct: true
  end

  
  config.vm.define "mongou" do |mongou|
    mongou.vm.box="ubuntu/trusty64"
    mongou.vm.hostname = "ubuntu-mongou"
    mongou.vm.network "private_network", ip: "192.168.33.31"
	#mongou.vm.network "forwarded_port", guest: 22, host: 2231, auto_correct: true
  end
  
  config.vm.define "lemp" do |lemp|
    lemp.vm.box="ubuntu/trusty64"
    lemp.vm.hostname = "ubuntu-lemp"
    lemp.vm.network "private_network", ip: "192.168.33.50"
	#lemp.vm.network "forwarded_port", guest: 22, host: 2250, auto_correct: true
	lemp.vm.network "forwarded_port", guest: 80, host: 15080, auto_correct: true
	lemp.vm.network "forwarded_port", guest: 443, host: 15043, auto_correct: true
  end

  config.vm.define "wplamp" do |wplamp|
    wplamp.vm.box="ubuntu/trusty64"
    wplamp.vm.hostname = "wp-ubuntu-lamp"
    wplamp.vm.network "private_network", ip: "192.168.33.51"
	#wplamp.vm.network "forwarded_port", guest: 22, host: 2251, auto_correct: true
	wplamp.vm.network "forwarded_port", guest: 80, host: 15180, auto_correct: true
	wplamp.vm.network "forwarded_port", guest: 443, host: 15143, auto_correct: true
  end
  
  config.vm.provider "virtualbox" do |v|
    v.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
	v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end

end
