# server-config

A VPS configuration using Traefik as a reverse proxy and Docker for containerization.

By default Traefik accepts HTTP and HTTPs connections.

Cloudfare handles with DNS and extra SSL configuration.

Architecture: `Internet > Cloudflare (HTTPS) > VPS > Traefik > Containers Docker`

```bash
# view traefik logs
docker compose exec traefik tail -f /var/log/traefik/traefik.log | jq .

# view logs of each request to traefik
docker compose exec traefik tail -f /var/log/traefik/access.log | jq .
```
