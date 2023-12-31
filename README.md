# Homelab with Docker Compose

Collection of Docker Compose files to easily install and manage your homelab. This includes containers I use myself. Feel free to suggest new containers of fork this repository and add your own.

## Included containers

| Applications                                                                                                         | Media                                                                                                        | Administration                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/home-assistant.png" width="24" /> Home Assistant | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/jellyfin.png" width="24" /> Jellyfin     | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/nginx-proxy-manager.png" width="24" /> Nginx Proxy Manager |
| <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/actual.png" width="24" /> Actual Budget          | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/jellyseerr.png" width="24" /> Jellyseerr | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/dozzle.png" width="24" /> Dozzle                           |
| <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/mealie.png" width="24" /> Mealie                 | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/prowlarr.png" width="24" /> Prowlarr*    | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/qbittorrent.png" width="24" /> qBitTorrent*                |
| <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/nextcloud.png" width="24" /> Nextcloud           | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/radarr.png" width="24" /> Radarr*        | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/uptime-kuma.png" width="24" /> Uptime Kuma                 |
| <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/homebox.png" width="24" /> Homebox               | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/sonarr.png" width="24" /> Sonarr*        | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/gluetun.png" width="24" /> Gluetun                         |
| <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/immich.png" width="24" /> Immich                 | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/bazarr.png" width="24" /> Bazarr*        | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/cloudflare.png" width="24" /> CloudFlare DDNS              |
|                                                                                                                      | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/readarr.png" width="24" /> Readarr*      | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/duplicati.png" width="24" /> Duplicati                     |
|                                                                                                                      | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/metube.png" width="24" /> Metube         | Docker Volume Backup                                                                                                           |
|                                                                                                                      | <img src="https://cdn.jsdelivr.net/gh/walkxcode/dashboard-icons/png/podgrab.png" width="24" /> Podgrab       | FlareSolverr                                                                                                                   |

Disclaimer: these containers are only used for managing legal Linux distro's. 

## Requirements

- [x] Docker and Docker Compose is installed on your system. See [Docker install documentation](https://docs.docker.com/engine/install/)
- [x] Your user has rights to run Docker. See [post-installation steps](https://docs.docker.com/engine/install/)
- [x] Create all required directories used for media storage.

## Folder structure

```
├── /opt
│  └── homelab (this repo)
|     ├── application folder
│     |  └── .env
│     |  └── compose.yaml
|     └── compose.yaml
├── /srv
│  └── homelab (docker data)
|  |  └── application folder
│  |     └── * (config & data folder)
│  |        └── *
|  └── backup
|      └── volume (backups by docker-volume-backup)
|      └── duplicati (backups by duplicati)
└── /mnt/storage (media storage)
   ├── nextcloud
   ├── photos
   ├── downloads
   │  ├── books
   │  ├── movies
   │  └── tv
   └── media
      ├── books
      ├── movies
      ├── podcasts
      ├── tv
      └── metube
```

## Installation

### Clone this repository

```shell
$ cd /opt
$ git clone https://github.com/shaunjanssens/homelab
```

### Change `.env` files for all containers

Each container has it's own `.env` file with container specific config. Each container contains and `README.md` with more info.

#### Getting user and group ID

By default, Docker containers run as `root`. This entails dangers, that's why most containers run as a non-root user.

```shell
$ id
```

The output of this command should be something like `uid=1000(homelabuser) gid=1000(homelabuser) groups=1000(homelabuser),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),105(lxd),994(docker)` when `1000` is your user and group id and `994` your Docker group.

### Create data directories for all containers

```shell
$ sudo mkdir /srv/homelab
$ cd /srv/homelab
$ sudo mkdir {actual-budget,duplicati,home-assistant,homebox,homer,immich-database,immich-machine-learning,immich-machine-learning-gecoding,immich-redis,immich-typesense,jellyfin,mealie,gluetun,qbittorrent,prowlarr,radarr,sonarr,readarr,bazarr,jellyseerr,metube,nextcloud,nextcloud-db,nginx-proxy-manager,podgrab,uptime-kuma}
```

### Change ownership of data and media directories

```shell
$ sudo chown -R $USER:$USER /srv/homelab
$ sudo chown -R $USER:$USER /media/storage
$ sudo chmod -R a=,a+rX,u+w,g+w /media/storage
```

### Start all containers

Change directory to the stack you want to start.

```shell
$ docker compose up -d
```

## Accessing containers

It's possible to access all apps with the server IP and container port but Nginx Proxy Manager is included to access the containers with a user-friendly domain. Cloudflare DDNS is also included to update your domains with your IP address. With Cloudflare it's possible to proxy all traffic so your IP address is not exposed.

## Dashboard

To get an overview of all containers there's a dashboard (homer) included. This dashboard needs some configuration to view all containers. There's also a custom theme included. [dashboard-icons](https://github.com/walkxcode/dashboard-icons) is used for app icons but it's also possible to use own images. A custom theme file is located at `homer/assets/custom.css`.

![Screenshot of Homer dashboard](assets/dashboard.jpg)

## Backup and restore

All Docker container config data is stored in `/srv/homelab` and is backed up every night to `/srv/backup/volume`. Duplicati is also installed to backup other data like media storage and Nextcloud data.

## Recommendations

- [LazyDocker](https://github.com/jesseduffield/lazydocker) for managing Docker containers
- [btop](https://github.com/aristocratos/btop) for monitoring server resources

## Roadmap

- [ ] Add [Diun](https://crazymax.dev/diun/) for getting notifications when a Docker image is updated