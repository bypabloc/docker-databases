## Entorno de desarrollo
- Ubuntu 21.10
- Docker version 20.10.14, build a224086
- Docker Compose version 1.26.0, build d4451659

### Requisitos previos:
1. Docker instalado en su servidor conforme a los pasos 1 y 2 de [Cómo instalar y usar Docker en Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
2. Docker Compose instalado en su servidor conforme el paso 1 de [Cómo instalar Docker Compose en Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)

## Comandos para arrancar el contenedor:
``` bash
sudo docker-compose up -d --build --remove-orphans --force-recreate
```

## Para realizar un restore en la db:
[MySql](/README-MYSQL.md)


## Nota, comandos docker:

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

## Si aparece un error como el siguiente:
``` bash
ERROR: Pool overlaps with other one on this address space
```
## Se puede solucionar con el comando:
``` bash
docker-compose down
docker network prune -f
```


## Configurar archivo template:
``` bash
git config --global ./.gitmessage ~/.gitmessage
```