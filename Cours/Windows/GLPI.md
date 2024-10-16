
## Requiements : 

- [serveur Debian]()
- [GLPI web app]()
- [service SSH]()

## Command Debian : 

`apt update & upgrade`
*Met à jour les paquets Debian*

`apt install openssh-server -y`
*Installe le service SSH pour une connexion à distance*

`ip a`
*Affiche les informations réseau*

`apt install apache2 php libapache2-mod-php mariadb-server -y`
*Installe les outils pour le serveur LAMP Linux Apache Maria DB PHP*

`apt install php-mysqli php-mbstring php-curl php-gd php-simplexml php-intl php-ldap php-apcu php-xmlrpc php-cas php-zip php-bz2 php-imap -y`
*Installe les dépendances à GLPI*

`mysql_secure_installation`
Sécurise l'accès à la BDD

`mysql -u root -p`
Se connecte à mysql

`create database bdd_glpi`
Créer la BDD pour GLPI

`grant all privileges on bdd_glpi.* to adminbdd_glpi@localhost identified by "your_password";`
?

`wget $url`
Télécharger un fichier sur le web

`tar -xvzf filename.tgz`
Décompresse l'archive

`chown -R www-data /var/www/html/glpi`
Ajoute des droits 

`nano filename`
Ouvre un éditeur de fichier

`systemctl restart apache2`
Redémarre le serveur apache2

`systemctl status apache2`
Affiche le statu du serveur apache2

`sudo usermod -l new_name old_name`
Changer le nom d'utilisateur old_name en new_name

`sudo passwd root`
Permet de changer le mdp d'un utilisateur (ou le root)

## GLPI agent

[GLPI agent](https://github.com/glpi-project/glpi-agent/releases)
[FusionInventory Agent](https://github.com/fusioninventory/fusioninventory-agent/releases/tag/2.6) **Depreciate**

## Maintenance

### niveau :
1. action simple (ex : nettoyage matériel)
2. opération majeur (ex : )
3. opération avec diagnostic (ex : )
4. travaux importants maintenance (ex : )
5. rénovation réparation (ex : remplacement de serveur)

### Type de maintenance

- corrective : d'une défaillance 
	- Réparation : résoudre le problème (curative)
	- Dépannage : en attente de réparation (palliative, provisoire)
- préventive : réduire probabilité de défaillance
	- systématique : périodicité
	- conditionnelle : Si ... alors intervention demandée

### Coût d'une panne

- Direct :
	- Temps passé
	- Pièces de remplacement
	- Intervention prestataire extérieur
- Indirect :
	- recyclage de pièce rebuté
	- reprise/retouche
	- perte prod pendant arrêt
	- pénalité retard livraison
	- coût main d'œuvre inoccupée panne

PCA : Plan Continuité de l'Activité
PCI : Plan Continuité de l'Informatique
avoir un serveur qui une copie conforme et continue du premier server. si un tombe l'autre reprend la main.

### planification sur GLPI