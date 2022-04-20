Vagrant.configure("2") do |config|
 config.vm.box_check_update = "false"
 config.vm.provider "virtualbox" do |vb|
   vb.memory = "1024"
 end
 config.vm.define "smaster" do |smaster|
   smaster.vm.hostname = "smaster"
   smaster.vm.box = "geerlingguy/centos7"
   smaster.vm.network :public_network, ip: "192.168.0.110",bridge: "wlp2s0"
   smaster.vm.network "forwarded_port", guest: "80", host: "8081"
   smaster.vm.provision "file", source: "./apache-playbook.yaml", destination: "/vagrant/apache-playbook.yaml"
   #Provision the webserver with Ansible
   smaster.vm.provision "ansible_local" do |ansible|
     ansible.playbook="apache-playbook.yaml"
   end
  end
  config.vm.define "sworker1" do |sworker1|
    sworker1.vm.hostname = "sworker1"
    sworker1.vm.box = "geerlingguy/centos7"
    sworker1.vm.network :public_network, ip: "192.168.0.111",bridge: "wlp2s0"
    sworker1.vm.network "forwarded_port", guest: "80", host: "8082"
    sworker1.vm.provision "file", source: "./apache-playbook.yaml", destination: "/vagrant/apache-playbook.yaml"
    #Provision the webserver with Ansible
    sworker1.vm.provision "ansible_local" do |ansible|
      ansible.playbook="apache-playbook.yaml"
    end
   end
   config.vm.define "sworker2" do |sworker2|
    sworker2.vm.hostname = "sworker2"
    sworker2.vm.box = "geerlingguy/centos7"
    sworker2.vm.network :public_network, ip: "192.168.0.112", bridge: "wlp2s0"
    sworker2.vm.network "forwarded_port", guest: "80", host: "8083"
    sworker2.vm.provision "file", source: "./apache-playbook.yaml", destination: "/vagrant/apache-playbook.yaml"
    #Provision the webserver with Ansible
    sworker2.vm.provision "ansible_local" do |ansible|
      ansible.playbook="apache-playbook.yaml"
    end
   end
end
