##Compte rendu TP2 linux2

Dans ce TP, nous devons réaliser la partie sous la paserelle cerbere2.info-ua. On va réaliser ce réseau local seulement avec des machines virtuelles avec Virtualbox.

Pour ce TP, on va utiliser la VM "Gateway" crée au TP1.

Premièrement, on va configurer la carte réseau de la machine virtuelle. On lui met en accès par pont.

Puis on va grâce à apt-get install installer le paquet openssh-server. C'est un serveur ssqh qui sera implanté sur la machine virtuelle.
On peut alors tester la connexion ssh sur l'hôte. 
On remarque que la connexion en tant qu'utilisateur courant fonctionne par contre l'accès en root n'est pas permis.

Puis on va modifier le port d'écoute du serveur ssh. Il suffit d'éditer le fichier sshd_config présent dans /etc/ssh/.
Rechercher la ligne avec le mot Port et changer le port pour qu'il écoute le port 26.
