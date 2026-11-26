## NGINX REPLICAS ON KUBERNETES

- Write a deployment that create 3 replicas of webservers host on vagrant.

### Objective:

- Creates 3 nginx replicas
- Sets resource limits (important for learning)
- Exposes via NodePort on port 30080
- Uses alpine image (smaller, faster)

### Vagrant Configuration :

- config.vm.box = Use Ubuntu 20.04
- config.vm.hostname = Name the VM "webserver"
- config.vm.network "forwarded_port" = Connect VM port 80 to your port 8080
- vb.memory = "1024" = Give VM 1GB RAM
- vb.cpus = 1 = Give VM 1 CPU core
- config.vm.provision = Automatically install nginx and create a web page

### Vagrant Configuration Objective
●​ Creates Ubuntu VM
●​ Installs the nginx web server automatically
●​ Forward VM port 80 to your port 8080

### Deploy the application
- Vagrant init ubuntu/jammy64
- Vagrant up
- kubectl apply -f nginx-deployment.yaml​

### Clean Up
- Stop vagrant: vagrant halt
- Remove the nginx deployment:
- kubectl delete -f nginx-deployment.yaml​