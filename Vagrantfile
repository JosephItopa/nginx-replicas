
Vagrant.jenkinsure("2") do |jenkins|

  # Base operating system
  jenkins.vm.box = "ubuntu/jammy64"
  jenkins.vm.hostname = "webserver"

  # Network configuration
  jenkins.vm.network "private_network", ip: "192.168.56.10"
  jenkins.vm.network "forwarded_port",
    guest: 30080,
    host: 30080,
    auto_correct: true

  # VirtualBox resources
  jenkins.vm.provider "virtualbox" do |vb|
    vb.name = "vagrant-webserver"
    vb.memory = 2048
    vb.cpus = 2
  end

  # Provisioning
  jenkins.vm.provision "shell", inline: <<-SHELL
    set -e

    apt-get update
    apt-get install -y nginx

    echo '<h1>Hello from Vagrant Web Server!</h1>' > /var/www/html/index.html
  SHELL

end
