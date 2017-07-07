## Mariadb service
```bash
docker run --name mariadb_1 -p 4306:3306 -v /home/ropa/mariadb/mysql:/var/lib/mysql --restart unless-stopped -e MYSQL_ROOT_PASSWORD=root -d mariadb
```
