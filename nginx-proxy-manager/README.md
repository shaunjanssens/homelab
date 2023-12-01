# Nginx Proxy Manager

Used for accessing your containers with a domain name.

- Website: https://nginxproxymanager.com/
- Github: https://github.com/NginxProxyManager/nginx-proxy-manager

## Application ports

- Web: 81

## Default credentials

|          |                   |
|----------|-------------------|
| Username | admin@example.com |
| Password | changeme          |

## Adding containers

Add a proxy host with the following parameters:

| Parameter             | Value                          |
|-----------------------|--------------------------------|
| domain names          | service.domain.com             |
| scheme                | http                           |
| Forward Hostname / IP | name of container (eg: mealie) |
| Forward Port          | port of container (eg: 9000)   |

https is strongly recommended if the domain name is an external domain name.