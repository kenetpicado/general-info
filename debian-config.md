### Configuración inicial de Debian 11

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
