# lampp
problem lampp (linux apache mysql php)
# Installasi
1.akses root
```
sudo -i
```
2.update package
```
apt-get update
```
3.install apache2
```
apt-get install apache2
```
4.install php
```
apt-get install php
```
5.install mysql
```
apt-get install mysql-server
```
6.install phpmyadmin
```
sudo apt-get install phpmyadmin
```

# Problem phpmyadmin
1.error mbstring
```
sudo apt-get install php-mbstring php7.0-mbstring php-gettext libapache2-mod-php7.0
```
2.error root login password
```
$mysql -u root

#set update root password
USE mysql;
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'admin';
Here 'admin' is your new password, yo can change it.
exit;

#or fix use 
USE mysql;
UPDATE user SET plugin='mysql_native_password' WHERE User='root';
FLUSH PRIVILEGES;
exit;

#atau update
>> UPDATE mysql.user SET Password=PASSWORD('new_password') WHERE User='root';
>> UPDATE mysql.user SET authentication_string =PASSWORD('new_password') WHERE User='root';

$ service mysql restart
```
3.Not pound phpmyaadmin
```
sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf
sudo a2enconf phpmyadmin.conf
sudo service apache2 reload
```
