# Define array of virtual machines
machines=[
  {
    :hostname => "arch",
    :ip => "192.168.100.10",
    :box => "https://dl.dropboxusercontent.com/u/31112574/arch64-20130801.box",
    :ram => 256,
  }
]

# Setup each machine in mentioned array
Vagrant.configure(2) do |config|
    config.vm.synced_folder ".", "/vagrant"
    machines.each do |machine|
        config.vm.define machine[:hostname] do |node|
            node.vm.box = machine[:box]
            node.vm.hostname = machine[:hostname]
            node.vm.network "private_network", ip: machine[:ip]
            node.vm.provider "virtualbox" do |vb|
                vb.customize ["modifyvm", :id, "--memory", machine[:ram]]
            end
        end
    end
end
