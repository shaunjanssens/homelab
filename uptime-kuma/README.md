# Uptime Kuma

Used for monitoring containers and other services.

- Website: https://uptime.kuma.pet/
- Github: https://github.com/louislam/uptime-kuma

## Installation

- Add Docker socket in `Settings > Docker Hosts > Setup Docker Host` to monitor Docker containers. `Docker Daemon: /var/run/docker.sock`

## Troubleshooting

### Error `connect EACCES /var/run/docker.sock` when adding Docker socket

This is a permissions issue. See https://github.com/louislam/uptime-kuma/issues/2248

Solution: set `PGID` to `docker` group id 