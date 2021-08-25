# vagrant-k8s

Descripción:

Este laboratorio automatiza en gran parte y hace flexible la generación de un cluster k8s vía Vagrant

Requisitos:
- vbox
- vagrant
- plugin de vagrant (la imagen vagrant "focal64" de ubuntu no monta bien las carpetas compartidas)
    - vagrant plugin install vagrant-vbguest

Pasos a seguir:
- colocarse en directorio del Vagrantfile
- vagrant up
- vagrant ssh kubemaster
- dos2unix ./resources/init-cluster/*
- ./resources/init-cluster/01-advertise.sh
- ./resources/init-cluster/02-preflights.sh
- ./resources/init-cluster/03-network.sh
- unir los nodos (el comando lo tenemos en un fichero ubicado en /home/vagrant/)
- ./resources/init-cluster/04-label.sh
- ./resources/init-cluster/05-metrics-server.sh
- ./resources/init-cluster/06-dashboard.sh

Tendremos accesible el dashboard a través de la URL (y el token para acceder en un log ubicado en /home/vagrant/): 

http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/
