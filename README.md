# server-config

A VPS configuration using Traefik as a reverse proxy and Docker for containerization.

By default Traefik accepts HTTP connections and Cloudfare handles with DNS and SSL configuration.

Architecture: `Internet > Cloudflare (HTTPS) > VPS (HTTP:80) > Traefik > Containers Docker`
