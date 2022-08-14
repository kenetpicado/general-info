# Laravel
## Comandos generales
- Instalar composer
```shell
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '906a84df04cea2aa72f40b5f787e49f22d4c2f19492ac310e8cba5b96ac8b64115ac402c8cd292b8a03482574915d1a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"

sudo mv composer.phar /usr/local/bin/composer
```
- Instalador laravel
```shell
composer global require laravel/installer
```

- Reconocer el comando laravel new; añadir al archivo .bashrc
```shell
export PATH=$PATH:$HOME/.config/composer/vendor/bin
```
- Crear proyecto
```shell
composer create-project laravel/laravel:^8.0 example-app
composer create-project laravel/laravel example-app
```
- Ver informacion de paquetes instalados
```shell
composer global show
```
- Ejecutar el servidor de prueba
```shell
php artisan serve
```
- Crear controlador
```shell
php artisan make:Controller AlumnoController
```
## Bases de datos
```shell
php artisan make:migration create_alumnos_table
php artisan migrate
php artisan migrate:rollback
php artisan migrate:reset
```
## Eloquent
- Al crear un modelo la opción "-a" se crean además todos los archivos con base al mismo modelo (Controlador, Migración, Request, etc.)
```shell
php artisan make:model Alumno -a
```

## Instalar Bootstrap
- Instalar parquete Laravel ui
```shell
composer require laravel/ui
```
- Instalar el scaffolding de Bootstrap
```shell
php artisan ui bootstrap
```
Install npm
```shell
npm install && npm run dev
```
- Añadir css y js al proyecto
```shell
<script type="text/javascript" src="{{asset('js/script.js')}}"></script>

<link href="{{asset('css/app.css')}}" rel="stylesheet">
```

### Otros comandos
- Generar llave
```shell
php artisan key:generate
```
- Limpiar caché
```shell
php artisa optimize:clear
```