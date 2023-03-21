# Apache

## Archivos de configuración de Apache para hosts virtuales

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
    DocumentRoot "/home/kenet/Documentos/GitHub/healthier/public"
    ServerName v1healthier.test
    ServerAlias *.v1healthier.test
    <Directory "/home/kenet/Documentos/GitHub/healthier/public">
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```
