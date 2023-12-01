# NextCloud

Used for file storage and more.

- Website: https://nextcloud.com/
- Github: https://github.com/nextcloud
- Docker image: https://docs.linuxserver.io/images/docker-nextcloud

## Application ports

- Web: 443 (https)

## Notes

- Make sure that the owner of `DATADIR` is the same user as `PUID:PGID`.

## Installation

- Data folder: /data
- Choose "MySQL/MariaDB" database
  - Database user: nextcloud
  - Database password: <NEXTCLOUD_MYSQL_PASSWORD>
  - Database name: nextcloud
  - Database host: nextcloud-db

## Usage

### Adding files not uploaded via web interface or Nextcloud sync client

`docker exec -it nextcloud occ files:scan --all`