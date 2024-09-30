
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