# Para Resturar y Respaldar necesitamos obtener el CONTAINER ID:

## Resturar
``` bash
cat <path-file-sql>.sql | sudo docker exec -i <container-id> mysql -u <user> --password=<password> <db-name>
```

``` bash
cat database.sql | sudo docker exec -i ae38154bc560 mysql -u root --password=123456 database-db
```

## Backup

``` bash
sudo docker exec <container-id> mysqldump -u <user> --password=<password> <db-name> > <path-file-sql>.sql
```

``` bash
sudo docker exec ae38154bc560 mysqldump -u root --password=123456 database-db > database.sql
```

