##Compte-rendu TP1 linux2

###Installation de la machine virtuelle

Pour installer une machine virtuelle debian, on a utiliser virtualbox. On crée la machine avec l'image disque de debian (on fait ici cependant une netinstall). On connecte pour l'instant la machine en NAT.
Puis on procéde à l'installation du système. Pour les logiciels, on ne choisit que la case "Utilitaires usuels du systeme".

Au démarrage de la session, on installe plusieurs logiciels qui vont nous servir : aptitude install lynx sudo tcpdump vim.

Puis on va accorder les droits à l'utilisateur de faire la commande sudo. Il faut alors ajouter dans le fichier /etc/sudoers une ligne donnant les droits à l'utilisateur.

##Clonage des VM

On va créer 3 nouvelles machines "Gateway", "Client" et "Serveur_web" en réalisant 3 clones intégrale de debian_base. 
Concrètement, on va cliquer sur notre VM et on va faire un clone intégral en réinitialisant les adresses MAC des cartes réseaux.

##Snapshot

On va créer un instantané de debian_base avec virtualbox pour sauvegarder la machine avant d'effectuer un rm qui va tout supprimer jusqu'à la racine.
Quand on effectue cette commande et qu'on redémarre le grub ne peut plus se lancer et le system entre en rescue mode.

Quand on restaure la VM au moment du snapshot, la machien démarre sans problème en revenant à son ancien état.

##Configuration réseau

On va modifier la configuration de la machine virtuelle "debian base" se sorte à avoir un accès par pont sur le réseau.
Si on tape la command "ip addr show", on peut visualiser son addresse ip.

Si alors on entre la commande lynx. Nous voilà sur un navigateur web en mode texte où l'on peut parcourir toutes les pages web
transcrites en texte.

