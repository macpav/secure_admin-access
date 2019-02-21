# secure_admin-access
Debloquez / sécurisez  vos accès d'administration de vos serveurs/vps dans le  cloud .

Unblock / secure your administration access to your servers / vps in the cloud .

prérequis= Debian GNU/Linux 9 ( debian-9.8.0-amd64-netinst.iso )
 apt-get  install sysv-rc-conf
 

### 1- Change standard port 

### 2- ipset 
   
apt-get install ipset

### 1- iptables
creer fichier firewal dans /etc/init.d/ 
vim.tiny firewall

chmod 755 firewall
update-rc.d firewall enable
update-rc.d firewall defaults


   
### 3- configure apache2 ,php7,mysql

apt-get install apache2
apt-get install php
apt-get install mysql-server
apt-get install php-mysql
apt-get install phpmyadmin
mkdir /var/www/connect

Limit visible information  -> /etc/apache2/conf-available/security.conf
   change "ServerTokens OS"   by   "ServerTokens Prod"
   change "ServerSignature On"   by   "ServerSignature Off"
   
Limit visible information  -> /etc/php/7.0/apache2/php.ini
   check if expose_php = Off
   
limit dos -> /etc/apache2/apache2.conf   
      MaxClients 150
      KeepAlive On
      MaxKeepAliveRequests 100
      KeepAliveTimeout 10
