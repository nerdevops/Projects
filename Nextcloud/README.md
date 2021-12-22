# Docker Gitea

<p align="center">
<a href="https://nextcloud.com/"><img src="https://download.logo.wine/logo/Nextcloud/Nextcloud-Logo.wine.png" width="100" height="200" alt="Gitea"></a><br/>
</p>


## Como Começar

1. Clonar o projecto para sua maquina virtual:
[Docker-compose](https://docs.docker.com/compose/install/) example:

```yaml
version: '2'

volumes:
  nextcloud:
  db:

services:
  db:
    image: mariadb
    restart: always
    command: --transaction-isolation=READ-COMMITTED --binlog-format=ROW --innodb-file-per-table=1 --skip-innodb-read-only-compressed
    volumes:
      - db:/var/lib/mysql
    environment:
      - MYSQL_ROOT_PASSWORD=nextcloud
      - MYSQL_PASSWORD=nextcloud
      - MYSQL_DATABASE=nextcloud
      - MYSQL_USER=nextcloud

  app:
    image: nextcloud
    restart: always
    ports:
      - 8080:80
    links:
      - db
    volumes:
      - nextcloud:/var/www/html
    environment:
      - MYSQL_PASSWORD=nextcloud
      - MYSQL_DATABASE=nextcloud
      - MYSQL_USER=nextcloud
      - MYSQL_HOST=db
```
2. Correr `docker-compose up -d` para criar e startar o Nextcloud
3. Configurar via Gui
