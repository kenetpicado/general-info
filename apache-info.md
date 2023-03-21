# Apache - Archivos de configuración de Apache para hosts virtuales

### Enable php version
```shell
sudo a2dismod php5
sudo a2enmod php7.0
```

### phpmyadmin.conf

```shell
Alias /phpmyadmin /var/www/phpmyadmin

<Directory /var/www/phpmyadmin>
    Options FollowSymLinks
    DirectoryIndex index.php
    AllowOverride all
</Directory>

<Directory /var/www/phpmyadmin/setup>
    Require all denied
</Directory>

<Directory /var/www/phpmyadmin/libraries>
    Require all denied
</Directory>
```

### Laravel Project
```shell
<VirtualHost *:80>
    DocumentRoot "/var/www/site"
    ServerName v1healthier.test
    ServerAlias *.v1healthier.test
    <Directory "/var/www/site">
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```
