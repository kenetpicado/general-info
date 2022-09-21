
### Configuracion para MySQL
- Modificar contraseña
```shell
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'yournewpassword';
```

Ejecutar sudo mysql_secure_installation para realizar las configuraciones necesarias en un ambiente de producción.

- Crear nuevo usuario y asignarle todos los permisos sobre una base de datos.
```shell
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
```

- Importar Base de datos
```shell
mysql -u username -p database_name < file.sql
```

- Exportar Base de datos
```shell
mysqldump -u root -p database_name > file.sql
```
