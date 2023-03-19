# ansible
#déploiement ansible. LAB avec vagrant
#Installation Ansible
Prerequis:
1 Master sur lequel est installer Ansible
2 nodes: python et ssh installer sur chaque node 


###Installer Vagrant et virtualbox
Assurez-vous que Vagrant est installé sur votre ordinateur avec le plugin VirtualBox installé. Si ce n'est pas le cas, installez VirtualBox et le plugin VirtualBox pour Vagrant.

Créez un nouveau répertoire pour votre projet Vagrant et placez-y un fichier Vagrantfile.

Dans le fichier Vagrantfile, définissez trois machines virtuelles : un hôte maître et deux nœuds avec le fournisseur VirtualBox.


Dans cet exemple, nous utilisons l'image Ubuntu 20.04 (ubuntu/focal64) pour toutes les machines virtuelles. Chaque machine a un nom d'hôte et une adresse IP privée définis. Nous avons également configuré la mémoire de la machine virtuelle pour chaque nœud à 2048 Mo.

Lancez les machines virtuelles avec la commande vagrant up --provider virtualbox.

Connectez-vous à l'hôte maître avec la commande vagrant ssh ansible-master.

Installez Ansible sur l'hôte maître en utilisant la commande sudo apt-get update && sudo apt-get install ansible -y.

Configurez les machines virtuelles dans le fichier /etc/ansible/hosts. Ajoutez les machines virtuelles comme suit :

[nodes]
node1 ansible_host=192.168.33.11
node2 ansible_host=192.168.33.12


Cela définit un groupe de nœuds appelé "nodes" et spécifie l'adresse IP de chaque nœud.

Testez la configuration en exécutant une commande d'Ansible sur les nœuds, par exemple ansible nodes -m ping.

Vous êtes maintenant prêt à utiliser Ansible pour gérer vos machines virtuelles. Vous pouvez écrire des playbooks pour automatiser les tâches de configuration et de déploiement.
