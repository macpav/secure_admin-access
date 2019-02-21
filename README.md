# secure_admin-access
Debloquez / sécurisez  vos accès d'administration de vos serveurs/vps dans le  cloud .

Unblock / secure your administration access to your servers / vps in the cloud .

prérequis= Debian GNU/Linux 9 ( debian-9.8.0-amd64-netinst.iso )
apt-get install apache2 mysql-server phpmyadmin
### 1- Change standard port 

### 1- iptables
vim.tiny firewall

chmod 755 firewall

### 2- Configure IPtables 
   
   % apt-get install ipset
   
### 3- configure apache2 

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
