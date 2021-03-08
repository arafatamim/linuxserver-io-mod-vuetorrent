# linuxserver-io-mod-vuetorrent
[VueTorrent](https://github.com/WDaan/VueTorrent) theme mod for LinuxServer.io's qBittorrent container

## Usage
Add an environment variable called `DOCKER_MODS` with the value `arafatamim/linuxserver-io-mod-vuetorrent` when creating the container.

Example: `docker-compose.yml`
```yml
...
qbittorrent:
  image: linuxserver/qbittorrent
  container_name: qbittorrent
  environment:
    - PUID=1000
    - PGID=1000
    - UMASK=022
    - WEBUI_PORT=9090
    - DOCKER_MODS=arafatamim/linuxserver-io-mod-vuetorrent
  volumes:
    - ./data/qbittorrent:/config
    - /home/user/Downloads:/downloads
  ports:
    - 6881:6881
    - 6881:6881/udp
    - 9090:9090
  restart: unless-stopped
```

## Sources
- [VueTorrent repo](https://github.com/WDaan/VueTorrent)
- [LinuxServer's qBittorrent on Docker Hub](https://hub.docker.com/r/linuxserver/qbittorrent)
