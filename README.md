# Información general / Configuraciones varias

## Configuración inicial de Debian 11

- Repositorios

```shell
deb http://deb.debian.org/debian/ bullseye main contrib non-free
deb-src http://deb.debian.org/debian/ bullseye main contrib non-free

deb http://security.debian.org/debian-security bullseye-security main contrib non-free
deb-src http://security.debian.org/debian-security bullseye-security main contrib non-free

deb http://deb.debian.org/debian/ bullseye-updates main contrib non-free
deb-src http://deb.debian.org/debian/ bullseye-updates main contrib non-free
```
- Paquetes básicos
```shell
apt-get install linux-headers-$(uname -r|sed 's/[^-]*-[^-]*-//') build-essential make automake cmake autoconf git aptitude synaptic curl qapt-deb-installer
```
- Añadir al archivo .bashrc
```shell
export PATH=$PATH:/usr/local/sbin:/usr/sbin:/sbin
```
- Usuario root en terminal de Debian: su -
- Añadir al grupo sudoers en el archivo /etc/sudoers

### Instalar tipografias
- Libres
```shell
sudo apt install fonts-freefont-ttf fonts-freefont-otf
```
- Microsoft:
```shell
sudo apt-get install ttf-mscorefonts-installer
```
### Instalar snap
```shell
sudo apt install snapd
sudo snap install snap-store
```

### Instalar PHP 7.4
```shell
sudo apt -y install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
sudo apt install php7.4
```
- Extensiones
```shell
sudo apt install php7.4-common php7.4-mysql php7.4-xml php7.4-xmlrpc php7.4-curl php7.4-gd php7.4-imagick php7.4-cli php7.4-dev php7.4-imap php7.4-mbstring php7.4-opcache php7.4-soap php7.4-zip php7.4-intl -y
```
### Añadir resolución para monitor externo
```shell
xrandr --newmode "1280x720_60.00"  74.48  1280 1336 1472 1664  720 721 724 746  -HSync +Vsyncc
xrandr --addmode VGA-1 1280x720_60.00
xrandr --output VGA-1 --mode 1280x720_60.00 
```
### Configurar SSH GitHub
- Generar llaves dentro de ~/.ssh
```shell
ssh-keygen -t ed25519 -C "example@gmail.com"
```
- Crear el archivo config en ~/.ssh
```shell
Host github.com
  HostName github.com
  User *
  IdentityFile ~/.ssh/key
  IdentitiesOnly yes
```
- Añadir contendio de la llave .pub a GitHub
- Comprobar conexion
```shell
ssh -T git@github.com
```
### Cambiar el origin Git
- SSH
```shell
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```
- HTTPS
```shell
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
```
- Ver origin
```shell
git remote -v
```

### Instalar Nodejs
```shell
curl -s https://deb.nodesource.com/setup_16.x | sudo bash
sudo apt update
sudo apt install nodejs
```
- Actualizar npm
```shell
npm install -g npm@8.14.0
```

### Instalar Bootstrap
- Crear una carpeta
- Crear un archivo origin.scss y pegar
```shell
@import "node_modules/bootstrap/scss/bootstrap.scss"
```
- Iniciar npm
```shell
npm init -y
```
- Instalar bootstrap
```shell
npm install bootstrap --save
```
- Instalar sass
```shell
npm install -g sass
```
- Compilar
```shell
sass --watch origin.scss style.css
```

### Abrir puerto 80 en servidor web
```shell
sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 587 -j ACCEPT
sudo netfilter-persistent save
```

### Archivo config.inc.php para phpmyadmin
```shell
<?php

declare(strict_types=1);

/**
 * This is needed for cookie based authentication to encrypt password in
 * cookie. Needs to be 32 chars long.
 */
$cfg['blowfish_secret'] = 'abcdefghijklmnopqrstuvwxyzabcdef'; /* YOU MUST FILL IN THIS FOR COOKIE AUTH! */

/* Servers configuration */
$i = 0;

/* First server */
$i++;
/* Authentication type */
$cfg['Servers'][$i]['auth_type'] = 'cookie';
/* Server parameters */
$cfg['Servers'][$i]['host'] = 'localhost';
$cfg['Servers'][$i]['compress'] = false;
$cfg['Servers'][$i]['AllowNoPassword'] = false;

/* Directories for saving/loading files from server */
$cfg['UploadDir'] = '';
$cfg['SaveDir'] = '';
```


