# Docker Qbittorrent

<p align="center">
<a href="https://www.qbittorrent.org/"><img src="https://raw.githubusercontent.com/emmercm/docker-qbittorrent/assets/qbittorrent.png"></a><br/>
</p>

## Como Começar

1. Copiar o conteudo do docker-compose.yml

```yaml
version: "3"

services:
  qbittorrent:
    image: emmercm/qbittorrent:latest
    restart: unless-stopped
    environment:
      - TZ=America/Sao_paulo
    ports:
      - 8080:8080
      - 6881:6881/tcp
      - 6881:6881/udp
    volumes:
      - /home/ubuntu/downloads:/downloads
```
2. Adicionar o stack no Portainer
3. Abrir a pagina http://IP-Maquina-Virtual:8080
4. Aproveitar

- User: admin
- Pass: adminadmin