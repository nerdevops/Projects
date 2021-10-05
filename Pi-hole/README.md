# Docker Pi-hole

<p align="center">
<a href="https://pi-hole.net"><img src="https://pi-hole.github.io/graphics/Vortex/Vortex_with_text.png" width="150" height="255" alt="Pi-hole"></a><br/>
</p>
<!-- Delete above HTML and insert markdown for dockerhub : ![Pi-hole](https://pi-hole.github.io/graphics/Vortex/Vortex_with_text.png) -->

## Como Começar

1. Clonar o projecto para sua maquina virtual:
[Docker-compose](https://docs.docker.com/compose/install/) example:

```yaml
version: "3"

# Mais info Aqui: https://github.com/pi-hole/docker-pi-hole/ and https://docs.pi-hole.net/
services:
  pihole:
    container_name: pihole
    image: pihole/pihole:latest
    ports:
      - "53:53/tcp"
      - "53:53/udp"
      - "67:67/udp"
      - "80:80/tcp"
    environment:
      TZ: 'America/Chicago'
      WEBPASSWORD: 'NerdevOps'
    cap_add:
      - NET_ADMIN
    restart: unless-stopped
```
2. Correr `docker-compose up -d` para criar e startar o pi-hole
3. Mudar o DNS do seu equipamento para o ip da maquina virtual em questão