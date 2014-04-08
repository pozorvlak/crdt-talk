$script = <<SCRIPT
sudo apt-get update
sudo apt-get install -y rubygems1.9 build-essential ruby1.9.1-dev
sudo gem install showoff
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://dev-jen1.hogarthww.prv/pypi/vagrant/precise64.box"
  config.vm.network :public_network
  config.vm.provision "shell", inline: $script
  config.vm.network :forwarded_port, host:9090, guest:9090
end
