Vagrant.configure(2) do |config|

    N = 3
    (1..N).each do |i|
      config.vm.define "pgsql#{i}" do |node|
        node.vm.box = "debian/bullseye64"
        #node.vm.box_url = "file://bullseye.box"
        #node.vm.box = "ubuntu/jammy64"
        node.vm.box_url = "file://../../vbox/deb-11.box"
        node.vm.synced_folder ".", "/vagrant", disabled: true
        node.vm.hostname = "pgsql-cluster#{i}"
        node.vm.network "private_network", ip:"192.168.56.10#{i}"
        node.vm.provider "virtualbox" do |vb|
          vb.memory = "1024"
          vb.name = "pgsql-cluster#{i}"
          vb.cpus = 2
        end
      end
    end
 
end