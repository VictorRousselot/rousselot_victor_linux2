##Compte rendu TP2 linux2

Dans ce TP, nous devons réaliser la partie sous la paserelle cerbere2.info-ua. On va réaliser ce réseau local seulement avec des machines virtuelles avec Virtualbox.

Pour ce TP, on va utiliser la VM "Gateway" crée au TP1.

Premièrement, on va configurer la carte réseau de la machine virtuelle. On lui met en accès par pont.

Puis on va grâce à apt-get install installer le paquet openssh-server. C'est un serveur ssh qui sera implanté sur la machine virtuelle.
On peut alors tester la connexion ssh sur l'hôte. 
On remarque que la connexion en tant qu'utilisateur courant fonctionne par contre l'accès en root n'est pas permis.

Puis on va modifier le port d'écoute du serveur ssh. Il suffit d'éditer le fichier sshd_config présent dans /etc/ssh/.
Rechercher la ligne avec le mot Port et changer le port pour qu'il écoute le port 26.

Maintenant on va échanger des clés SSH pour ne plus avoir à taper son mot de passe lors de la connexion : 
on exécute la commande `ssh-keygen -t rsa`. Une clé privé et publique seront alors créés et placés dans ~/.ssh/. Ce sont els fichiers id_rsa et id_rsa.pub.

On va ensuite donner un exemplaire de notre clé publique au serveur avec la commande `ssh-copy-id -i ~/.ssh/id_rsa.pub -p 26 "rousselotv@192.168.99.52"`. On doit alors donner le mot de passe de connexion. Mais ici, l'agent ssh n'est pas activé.
Pour l'activer, il faut utiliser ces commandes : `eval ssh-agent -s` et `ssh-add`.

On peut donc maintenant se connecter en ssh à la VM Gateway sans rentrer à chaque fois nos mots de passe.

##Serveur DHCP

Avant d'installer notre serveur dhcp, on va ajouter 2 cartes réseaux avec virtualbox en accès par pont. Puis on va aller éditer 
le fichier interfaces présent dans /etc/network/. On va ici configurer notre interface eth1 qui sera l'interface qui communique avec le réseau du serveur web :





