# Información general / Configuraciones varias

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

- Cambiar entre diferentes versiones
```shell
update-alternatives --config php 
```
### Añadir resolución para monitor externo
```shell
xrandr --newmode "1280x720_60.00"  74.48  1280 1336 1472 1664  720 721 724 746  -HSync +Vsyncc
xrandr --addmode VGA-1 1280x720_60.00
xrandr --output VGA-1 --mode 1280x720_60.00 
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
