IMAGE_NAME = "bento/ubuntu-18.04"

Vagrant.configure("2") do |config|
    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
    end

    config.vm.define "slurm-master" do |master|
        master.vm.box = IMAGE_NAME
        master.vm.network "private_network", ip: "192.168.50.11"
        master.vm.hostname = "slurm-master"

		master.vm.provision "ansible" do |ansible|
			ansible.playbook = "playbooks/slurm-node-playbook.yml"
			ansible.extra_vars = {
				node_ip: "192.168.50.11",
			}
		end

    end

end
