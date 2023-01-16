
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