Vagrant.configure("2") do |config|
  config.vm.define "machine1" do |machine1|
  	machine1.vm.box = "ubuntu/trusty64"
	machine1.vm.network "private_network", ip:"192.168.77.60"
	machine1.vm.hostname = "machine1"
  end

  config.vm.define "machine2" do |machine2|
  	machine2.vm.box = "ubuntu/trusty64"
 	machine2.vm.network "private_network", ip:"192.168.77.61"
	machine2.vm.hostname = "machine2" 
  end

  config.ssh.insert_key=false
 
  #config.vm.network "forwarded_port", guest:80, host:8080
  #config.vm.network "forwarded_port", guest:22, host:2220  
 
  config.vm.provision "ansible" do |ansible|
  	ansible.verbose="vvv"
	ansible.playbook="playbook.yml"
  end
end
