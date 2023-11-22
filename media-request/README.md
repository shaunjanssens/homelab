# Media request

Use Servarr and TRaSH guides for setting up qBitTorrent, Prowlarr, Radarr, Sonarr and Bazarr. See: https://wiki.servarr.com/ & https://trash-guides.info/

## Gluetun

- Github: https://github.com/qdm12/gluetun

### Configuration

Check the required config variables for your VPN provider. See: https://github.com/qdm12/gluetun-wiki/tree/main/setup/providers

## qBitTorrent

- Website: https://www.qbittorrent.org/
- Docker image: https://docs.linuxserver.io/images/docker-qbittorrent/

### Default credentials

|          |            |
|----------|------------|
| Username | admin      |
| Password | adminadmin |


## Prowlarr

- Website: https://prowlarr.com/
- Github: https://github.com/Prowlarr/Prowlarr
- Docker image: https://docs.linuxserver.io/images/docker-prowlarr/

### Notes

- Use `localhost:6010` as host and port when adding qBitTorrent

## Radarr

- Website: https://radarr.video/
- Github: https://github.com/Radarr/Radarr
- Docker image: https://docs.linuxserver.io/images/docker-radarr/

### Notes

- Use `localhost:6010` as host and port when adding qBitTorrent

### Notes

- Use `localhost:6010` as host and port when adding qBitTorrent

## Sonarr

- Website: https://sonarr.tv/
- Github: https://github.com/Sonarr/Sonarr
- Docker image: https://docs.linuxserver.io/images/docker-sonarr/

### Notes

- Use `localhost:6010` as host and port when adding qBitTorrent

## Readarr

- Website: https://readarr.com/
- Github: https://github.com/Readarr/Readarr
- Docker image: https://docs.linuxserver.io/images/docker-readarr/

## Bazarr

- Website: https://www.bazarr.media/
- Github: https://github.com/morpheus65535/bazarr
- Docker image: https://docs.linuxserver.io/images/docker-bazarr/

## Metube

- Github: https://github.com/alexta69/metube

### Watching YouTube videos in Jellyfin

Install Jellyfin YouTube Metadata plugin for Jellyfin. See: https://github.com/ankenyr/jellyfin-youtube-metadata-plugin#installing-from-repository-recommended

## Podgrab

- Github: https://github.com/akhilrex/podgrab

## Jellyseerr

- Github: https://github.com/Fallenbagel/jellyseerr

### Notes

- Use `http://jellyfin:8096` as url for Jellyfin
- Use `http://gluetun:7878` as url for Radarr
- use `http://gluetun:8989` as url for Sonarr

## FlareSolverr

- Github: https://github.com/FlareSolverr/FlareSolverr
