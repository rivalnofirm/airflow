Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.synced_folder "../../", "/opt/airflow"
  # Assign static IP 
  config.vm.network "public_network", ip: "192.168.0.17"
  
  config.vm.provider "virtualbox" do |vb|
    config.vm.hostname = "swarm-leader"
    # RAM 
    vb.memory = "4096"
  end
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y curl 
  SHELL
end