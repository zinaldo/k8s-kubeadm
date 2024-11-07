Vagrant.configure("2") do |config|
    (1..1).each do |i|
        config.vm.define "master-#{i}" do |k8s|
            k8s.vm.box = "ubuntu/focal64"
            k8s.vm.hostname = "master-#{i}"
            k8s.vm.network "private_network", ip: "192.168.56.1#{i}"

            k8s.ssh.insert_key = false
            k8s.ssh.private_key_path = ['~/.vagrant.d/insecure_private_key', '~/.ssh/id_rsa']
            k8s.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/authorized_keys"

            k8s.vm.provider "virtualbox" do |vb|
              vb.gui = false
              vb.cpus = 2
              vb.memory = "2048"
            end
        end
    end

    (1..2).each do |i|
        config.vm.define "worker-#{i}" do |k8s|
            k8s.vm.box = "ubuntu/focal64"
            k8s.vm.hostname = "worker-#{i}"
            k8s.vm.network "private_network", ip: "192.168.56.2#{i}"

            k8s.ssh.insert_key = false
            k8s.ssh.private_key_path = ['~/.vagrant.d/insecure_private_key', '~/.ssh/id_rsa']
            k8s.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/authorized_keys"

            k8s.vm.provider "virtualbox" do |vb|
              vb.gui = false
              vb.cpus = 1
              vb.memory = "2048"
            end
        end
    end
end