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
### Laravel + API
```shell
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName www.laravel.test
    ServerAlias laravel.test
    DocumentRoot /var/www/laravel/public

    <Directory /var/www/laravel/public>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        allow from all
        Require all granted
        Options +FollowSymLinks
        RewriteEngine On
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteRule ^ index.php [L]
    </Directory>
</VirtualHost>
```

### Solo Laravel
```shell
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName www.laravel.test
    ServerAlias laravel.test
    DocumentRoot /var/www/laravel/public/

    <Directory /var/www/laravel/public/>
        Options +FollowSymLinks
        RewriteEngine On
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteRule ^ index.php [L]
    </Directory>
</VirtualHost>
```
