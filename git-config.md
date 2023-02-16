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
Añadir contendio de la llave .pub a GitHub
- Comprobar conexion
```shell
ssh -T git@github.com
```
### Cambiar el origin
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
### Eliminar todas las ramas excepto master
```shell
git branch | grep -v "master" | xargs git branch -D
```
