Vagrant.configure("2") do |config|
  config.vm.box = "trusty"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  #config.vm.network :forwarded_port, guest: 9200, host: 9200

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/dev.yml"
    ansible.verbose = "v"
  end

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--cpus", "2"]
    v.customize ["modifyvm", :id, "--memory", "4048"]
  end
end