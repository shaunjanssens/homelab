# Home Assistant

Used for managing your smart home.

- Website: https://www.home-assistant.io/
- Github: https://github.com/home-assistant/core
- Docker image: https://docs.linuxserver.io/images/docker-homeassistant/

## Application ports

- Web: 8123

## Reverse proxy

Adding Home Assistant to Nginx Proxy Manager is different than other containers because the `netword_mode` is `host`.

### Add http config to Home Assistant

Add the following code to `configuration.yaml` and restart container.

```yaml
http:
  use_x_forwarded_for: true
  trusted_proxies: 172.0.0.0/8
```

### Add Home Assistant to Nginx Proxy Manager

Add a proxy host with the following parameters:

| Parameter             | Value                                |
|-----------------------|--------------------------------------|
| domain names          | home.domain.com                      |
| scheme                | http                                 |
| Forward Hostname / IP | local IP of server (eg 192.168.0.10) |
| Forward Port          | 8123                                 |
| Websockets Support    | enabled                              |

https is strongly recommended if the domain name is an external domain name.