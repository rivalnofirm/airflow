Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 1
    vb.memory = "512"
    vb.linked_clone = true
  end 
  
  config.vm.define "airflow" do |airflow|
    airflow.vm.network :private_network, ip: "192.168.56.3"
  end
  config.vm.synced_folder "../../", "/opt/airflow"
  config.vm.provision "shell", inline: <<-SHELL
  apt-get update
  apt-get install -y curl 
  SHELL
end