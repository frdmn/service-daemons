# Define array of virtual machines
machines=[
  {
    :hostname => "arch",
    :ip => "192.168.100.10",
    :box => "https://dl.dropboxusercontent.com/u/31112574/arch64-20130801.box",
    :ram => 256,
  },
  {
    :hostname => "centos6",
    :ip => "192.168.100.102",
    :box => "http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-x86_64-v20131103.box",
    :ram => 256,
  },
  {
    :hostname => "debian",
    :ip => "192.168.100.103",
    :box => "http://dl.dropbox.com/u/54390273/vagrantboxes/Squeeze64_VirtualBox4.2.4.box",
    :ram => 256,
  },
  {
    :hostname => "ubuntu",
    :ip => "192.168.100.104",
    :box => "http://goo.gl/8kWkm",
    :ram => 256,
  },
  {
    :hostname => "gentoo",
    :ip => "192.168.100.105",
    :box => "https://dl.dropboxusercontent.com/s/0e23qmbo97wb5x2/gentoo-20131029-i686-minimal.box",
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
