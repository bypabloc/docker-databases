
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

### Al intentar levantar con `docker-compose up -d --build --remove-orphans --force-recreate`
### Si aparece un error como el siguiente 
[Example](/assets/images/11027-Failed-to-execute-script docker-compose.jpg)
``` bash
[11027] Failed to execute script docker-compose
```
### Se puede solucionar con el comando:
``` bash
rm ~/.docker/config.json
```
Solucion encontrada en [Github.com/docker/for-win](https://github.com/docker/for-win/issues/12355)

![Captura del error](../assets/images/11027-Failed-to-execute-script%20docker-compose.jpg)
