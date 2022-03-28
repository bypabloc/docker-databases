## Entorno de desarrollo
- Ubuntu 20.04.03
- Docker version 20.10.11, build dea9396
- Composer version 2.2.3 2021-12-31 12:18:53

### Requisitos previos:
1. Docker instalado en su servidor conforme a los pasos 1 y 2 de [Cómo instalar y usar Docker en Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
2. Docker Compose instalado en su servidor conforme el paso 1 de [Cómo instalar Docker Compose en Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)

## Comandos para arrancar el contenedor:
``` bash
# https://shouts.dev/articles/dockerize-a-laravel-app-with-apache-mariadb

sudo docker-compose build --no-cache
sudo docker-compose up -d --build --remove-orphans
sudo docker exec appinteli-laravel-app php --version
sudo docker exec appinteli-laravel-app php artisan --version
sudo docker exec -it appinteli-laravel-app bash
chmod 0777 storage -R
composer install
npm install && npm run watch
sudo docker exec appinteli-laravel-app npm run watch
php artisan serve --host 0.0.0.0 --port 8080
```

## Nota, comandos docker:

### Comandos para ver el log de un contenedor:
``` bash
sudo docker-compose logs -t -f web
```
### Comandos para bajar todos los contenedores:
``` bash
sudo docker-compose down
```
### Comandos para bajar todos los contenedores:
``` bash
sudo docker rm -f $(docker ps -a -q)
```
### Comandos para bajar todas las imagenes:
``` bash
sudo docker rmi -f $(docker images -aq)
```

### Comandos para bajar todos los volumenes:
``` bash
sudo docker volume rm $(docker volume ls -q)
```
### Para eliminar todas las imagenes que no estan usadas por contenedores existentes, usa la opcion -a:
``` bash
docker image prune -a
```

## Si el puerto esta ocupado, se puede usar el comando para liberarlo:
``` bash
lsof -t -i tcp:8000 | xargs kill -9
```

## Notas de comandos de git:
## Borrar archivos o directorios con seguimiento del local:
``` bash
git rm -r --cached nombre_directorio/
```

## Configurar archivo template:
``` bash
git config --global ./.gitmessage ~/.gitmessage
```
