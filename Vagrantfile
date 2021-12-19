servers=[
  {
    :hostname => "docker1",
    :ip => "10.10.10.1",
    :box => "gusztavvargadr/docker-linux",
    :ram => 1024,
    :cpu => 1
  },
  {
    :hostname => "docker2",
    :ip => "10.10.10.2",
    :box => "gusztavvargadr/docker-linux",
    :ram => 1024,
    :cpu => 1
  },
  {
    :hostname => "docker3",
    :ip => "10.10.10.3",
    :box => "gusztavvargadr/docker-linux",
    :ram => 1024,
    :cpu => 1
  }
]

Vagrant.configure(2) do |config|
    servers.each do |machine|
        config.vm.define machine[:hostname] do |node|
            node.vm.box = machine[:box]
            node.vm.hostname = machine[:hostname]
            node.vm.network "public_network", ip: machine[:ip], bridge: "YOUR_NET_INTERFACE"
            node.vm.provider "virtualbox" do |vb|
                vb.customize ["modifyvm", :id, "--memory", machine[:ram]]
 	        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
                vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
                vb.customize ['modifyvm', :id, '--graphicscontroller', 'vmsvga']
                vb.customize ['modifyvm', :id, '--vram', '128']
            end
        end
    end
end
