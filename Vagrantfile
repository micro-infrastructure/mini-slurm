IMAGE_NAME = "bento/ubuntu-18.04"
N = 1

Vagrant.configure("2") do |config|
    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
    end

	(1..N).each do |i|
		config.vm.define "node-#{i}" do |node|
			node.vm.box = IMAGE_NAME
			node.vm.network "private_network", ip: "192.168.50.#{i + 10}"
			node.vm.hostname = "node-#{i}"
			node.vm.provision "ansible" do |ansible|
				ansible.playbook = "playbooks/slurm-node-playbook.yml"
				ansible.extra_vars = {
					node_ip: "192.168.50.#{i + 10}",
				}
			end

		end
	end

end
