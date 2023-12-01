# Media request

Use Servarr and TRaSH guides for setting up qBitTorrent, Prowlarr, Radarr, Sonarr and Bazarr. See: https://wiki.servarr.com/ & https://trash-guides.info/

## Gluetun

Used for connecting containers with a VPN

- Github: https://github.com/qdm12/gluetun

### Configuration

Check the required config variables for your VPN provider. See: https://github.com/qdm12/gluetun-wiki/tree/main/setup/providers

## qBitTorrent

Used for downloading torrents

- Website: https://www.qbittorrent.org/
- Docker image: https://docs.linuxserver.io/images/docker-qbittorrent/

### Application ports

- Web: 8080

### Default credentials

|          |            |
|----------|------------|
| Username | admin      |
| Password | adminadmin |

## Prowlarr

Used for managing indexers

- Website: https://prowlarr.com/
- Github: https://github.com/Prowlarr/Prowlarr
- Docker image: https://docs.linuxserver.io/images/docker-prowlarr/

### Application ports

- Web: 9696

## Radarr

Used for managing movies

- Website: https://radarr.video/
- Github: https://github.com/Radarr/Radarr
- Docker image: https://docs.linuxserver.io/images/docker-radarr/

### Application ports

- Web: 7878

## Sonarr

User for managing tv shows

- Website: https://sonarr.tv/
- Github: https://github.com/Sonarr/Sonarr
- Docker image: https://docs.linuxserver.io/images/docker-sonarr/

### Application ports

- Web: 8989

## Readarr

Used for managing e-books

- Website: https://readarr.com/
- Github: https://github.com/Readarr/Readarr
- Docker image: https://docs.linuxserver.io/images/docker-readarr/

### Application ports

- Web: 8787

## Bazarr

Used for managing subtitles

- Website: https://www.bazarr.media/
- Github: https://github.com/morpheus65535/bazarr
- Docker image: https://docs.linuxserver.io/images/docker-bazarr/

### Application ports

- Web: 6767

## FlareSolverr

Used for bypassing Cloudflare

- Github: https://github.com/FlareSolverr/FlareSolverr

## Jellyseerr

Used for requesting media via Radarr and Sonarr

- Github: https://github.com/Fallenbagel/jellyseerr

### Application ports

- Web: 5055

### Notes

- Use `http://jellyfin:8096` as url for Jellyfin
- Use `http://gluetun:7878` as url for Radarr
- use `http://gluetun:8989` as url for Sonarr