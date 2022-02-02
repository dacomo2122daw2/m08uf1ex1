Vagrant.configure("2") do |config|
  config.vm.box = "generic/debian10"
  config.vm.hostname = "dacomo"
  config.vm.provider "virtualbox" do |v|
    # v.gui = true
    v.name = "m08uf1ex1"
    v.memory = 2048
    v.cpus = 1
    v.customize ['modifyvm', :id, '--clipboard', 'bidirectional']     
  end

  config.vm.network "forwarded_port", guest: 80, host: 18080
       
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -y
    sudo apt-get upgrade -y
    sudo apt-get install -y net-tools    
  SHELL

end
