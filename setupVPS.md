sudo apt update

sudo apt upgrade

sudo apt install apache2
sudo a2enmod rewrite
sudo a2enmod ssl
sudo systemctl restart apache2

sudo apt install git

cd ~/.ssh

ssh-keygen -t ed25519 -C "kenetpicado1@gmail.com"

crear archivo de cconfiguracion
ost github.com
 HostName github.com
 User *
 IdentityFile ~/.ssh/kenetpicado
 IdentitiesOnly yes

copiar el codigo de la llave publica en gh
probar conexion
ssh -T git@github.com

sudo apt install php8.1

sudo apt install php8.1-common php8.1-mysql php8.1-xml php8.1-xmlrpc php8.1-curl php8.1-gd php8.1-imagick php8.1-cli php8.1-dev php8.1-imap php8.1-mbstring php8.1-opcache php8.1-soap php8.1-zip php8.1-intl -y

instalar composer
https://getcomposer.org/download/

install mysq
sudo apt install mysql-server

sudo mysql

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';

exit

ejecutar
sudo mysql_secure_installation
rremove todos los usuarios y base de datos que siguere

entrar
sudo mysql -u root -p

ejecutar para volver a iniciar el usuario root sin contrasena
ALTER USER 'root'@'localhost' IDENTIFIED WITH auth_socket;

