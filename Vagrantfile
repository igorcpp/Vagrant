Vagrant.configure("2") do |config|
    servers=[
        {
          :hostname => "control",
          :box => "ubuntu/bionic64",
          :ip => "192.168.48.1",
          :ssh_port => '2200'
        },
        {
          :hostname => "node1",
          :box => "ubuntu/bionic64",
          :ip => "192.168.48.10",
          :ssh_port => '2201'
        },
        {
          :hostname => "node2",
          :box => "ubuntu/bionic64",
          :ip => "192.168.48.20",
          :ssh_port => '2202'
        },
        {
          :hostname => "node3",
          :box => "ubuntu/bionic64",
          :ip => "192.168.48.30",
          :ssh_port => '2203'
        }
      ]

    servers.each do |machine|
        config.vm.define machine[:hostname] do |node|
            node.vm.box = machine[:box]
            node.vm.hostname = machine[:hostname]
            node.vm.network :private_network, ip: machine[:ip]
            node.vm.network "forwarded_port", guest: 22, host: machine[:ssh_port], id: "ssh"
            node.vm.provider :virtualbox do |vb|
                vb.customize ["modifyvm", :id, "--memory", 512]
                vb.customize ["modifyvm", :id, "--cpus", 1]
            end
        end
    end
end