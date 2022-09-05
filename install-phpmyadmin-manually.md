# Instalar phpmyadmin en Ubuntu 20.04 manualmente

- Descargar phpmyadmin dentro de */var/www*
```shell
wget https://files.phpmyadmin.net/phpMyAdmin/5.2.0/phpMyAdmin-5.2.0-all-languages.zip
```
- Descomprimir
```shell
unzip phpMyAdmin-5.0.2-all-languages.zip
```
Es recomendable renombrar la carpeta por un nombre mas simple como **phpmyadmin**
```shell
mv phpMyAdmin-5.0.2-all-languages phpmyadmin
```
- Dentro de phpmyadmin, crear el archivo **config.inc.php** con el siguiente contenido

```shell
<?php

declare(strict_types=1);

/**
 * This is needed for cookie based authentication to encrypt password in
 * cookie. Needs to be 32 chars long.
 */
$cfg['blowfish_secret'] = ''; /* YOU MUST FILL IN THIS FOR COOKIE AUTH! */

/**
 * Servers configuration
 */
$i = 0;

/**
 * First server
 */
$i++;

/* Authentication type */
$cfg['Servers'][$i]['auth_type'] = 'cookie';

/* Server parameters */
$cfg['Servers'][$i]['host'] = 'localhost';
$cfg['Servers'][$i]['compress'] = false;
$cfg['Servers'][$i]['AllowNoPassword'] = false;

/**
 * Directories for saving/loading files from server
 */
$cfg['UploadDir'] = '';
$cfg['SaveDir'] = '';
```
- Crear el archivo de configuracion **phpmyadmin.conf** en */etc/apache2/sites-available/*

```shell
Alias /phpmyadmin /var/www/phpmyadmin

<Directory /var/www/phpmyadmin>
    Options FollowSymLinks
    DirectoryIndex index.php
    AllowOverride all
</Directory>

# Disallow web access to directories that don't need it
<Directory /var/www/phpmyadmin/setup>
    Require all denied
</Directory>

<Directory /var/www/phpmyadmin/libraries>
    Require all denied
</Directory>
```
- Habilitar el sitio
```shell
sudo a2ensite phpmyadmin.conf
```
- Reiniciar Apache
```shell
sudo systemctl restart apache2.service
```
Si todo ha salido bien, puede escribir en su navegador *localhost/phpmyadmin*