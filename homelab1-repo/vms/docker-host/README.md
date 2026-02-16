# Docker Host VM — 192.168.5.8

Use this VM to run auxiliary containers. For services that already have their own VMs (Immich, Stash, Paperless-ngx), you can still keep small helpers here (reverse proxy, monitoring, etc.).

Example `docker-compose.yml` (Traefik + Portainer as helpers):

```yaml
version: "3.8"
services:
  traefik:
    image: traefik:v3.0
    command:
      - "--api.dashboard=true"
      - "--providers.docker=true"
      - "--entrypoints.web.address=:80"
      - "--entrypoints.websecure.address=:443"
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - "/var/run/docker.sock:/var/run/docker.sock:ro"
    restart: unless-stopped

  portainer:
    image: portainer/portainer-ce:latest
    ports:
      - "9000:9000"
    volumes:
      - "/var/run/docker.sock:/var/run/docker.sock"
      - "portainer_data:/data"
    restart: unless-stopped

volumes:
  portainer_data: {}
```
