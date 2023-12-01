# Duplicati

Used for backing up files and storing them remotely

- Website: https://www.duplicati.com/
- Github: https://github.com/duplicati/duplicati
- Docker image: https://docs.linuxserver.io/images/docker-duplicati

## Application ports

- Web: 8200

## Setup

Every night all container volumes are backed up to `/media/storage/backup/volume/<application name>`. `/media/storage/` is mounted as `/source/storage` and `/opt/homelab` as `/source/stacks`. These contain all the data that should be backed up.