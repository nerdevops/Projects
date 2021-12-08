# Docker Gitea

<p align="center">
<a href="https://gitea.io/en-us/"><img src="https://gitea.io/images/gitea.png" width="280" height="280" alt="Gitea"></a><br/>
</p>


## Como Começar

1. Clonar o projecto para sua maquina virtual:
[Docker-compose](https://docs.docker.com/compose/install/) example:

```yaml
version: "3"

networks:
  gitea:
    external: false

services:
  server:
    image: gitea/gitea
    container_name: gitea
    environment:
      - USER_UID=1000
      - USER_GID=1000
    restart: always
    networks:
      - gitea
    volumes:
      - data_gitea:/data
      - /etc/timezone:/etc/timezone:ro
      - /etc/localtime:/etc/localtime:ro
    ports:
      - "3000:3000"
      - "2234:22"
volumes:
  data_gitea: {}
```
2. Correr `docker-compose up -d` para criar e startar o getea
3. Configurar via Gui