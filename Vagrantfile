
Vagrant.configure("2") do |config|

  # Base operating system
  config.vm.box = "ubuntu/jammy64"
  config.vm.hostname = "webserver"

  # Network configuration
  config.vm.network "forwarded_port",
    guest: 80,
    host: 8080,
    auto_correct: true

  # VirtualBox resources
  config.vm.provider "virtualbox" do |vb|
    vb.name = "vagrant-webserver"
    vb.memory = 2048
    vb.cpus = 2
  end

  # Provisioning
  config.vm.provision "shell", inline: <<-SHELL
    set -e

    apt-get update
    apt-get install -y nginx

    echo '<h1>Hello from Vagrant Web Server!</h1>' > /var/www/html/index.html
  SHELL

end
