Vagrant.configure(2) do |config|
	config.vm.define "jenkins" do |jenkins|
		jenkins.vm.box = "ubuntu/trusty64"
		jenkins.vm.network "private_network", ip: "192.168.0.252"
		jenkins.vm.provider "virtualbox" do |jenkinsv|
			jenkinsv.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
			jenkinsv.memory = 4096
			jenkinsv.cpus = 2
		end
		jenkins.vm.hostname = "jenkins.puneet.com"
		jenkins.vm.provision "chef_solo" do |chef|
			chef.add_recipe "ci"
		end
	end
end

