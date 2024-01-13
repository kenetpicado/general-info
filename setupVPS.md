1. Update system

```
sudo apt update
sudo apt upgrade
```

2. Install and configure Apache

```
sudo apt install apache2
sudo a2enmod rewrite
sudo a2enmod ssl
sudo systemctl restart apache2
```

3. Install and configure Git
```
sudo apt install git
```
- Configure SSH
```
cd ~/.ssh

ssh-keygen -t ed25519 -C "kenetpicado1@gmail.com"

Host github.com
 HostName github.com
 User *
 IdentityFile ~/.ssh/private-key-file
 IdentitiesOnly yes
```

- Copiar el código de la llave publica en GitHub y probar conexión
```
ssh -T git@github.com
```

5. Install php
```
sudo apt install php8.1
sudo apt install php8.1-common php8.1-mysql php8.1-xml php8.1-xmlrpc php8.1-curl php8.1-gd php8.1-imagick php8.1-cli php8.1-dev php8.1-imap php8.1-mbstring php8.1-opcache php8.1-soap php8.1-zip php8.1-intl -y
```

6. Install Composer: `https://getcomposer.org/download/`

7. Install MySQL
```
sudo apt install mysql-server
```

- Set password for root user (required to run `mysql_secure_installation`)
```
sudo mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
exit
```
- Run mysql_secure_installation
```
sudo mysql_secure_installation
```

- Run to restart root user without password (Optional)
```
sudo mysql -u root -p
ALTER USER 'root'@'localhost' IDENTIFIED WITH auth_socket;
```

