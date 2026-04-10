# server-config

A VPS configuration using **Traefik** as a reverse proxy and **Docker** for containerization, automatic SSL certificates, rate limit and security good practices.

By default Traefik accepts HTTP and HTTPs connections.

Cloudfare handles with DNS and extra SSL configuration.

Architecture: `Internet > Cloudflare > VPS > Traefik > Containers Docker`

## Setup

Clone and configure environment:

```bash
cp .env.example .env
# Edit .env with your domain and email
```

Start services:

```bash
docker compose up -d
```

Verify everything is running:

```bash
docker ps
```

Test your API:

```bash
curl https://api.yourdomain.com/health
```

## Common Commands

```bash
# Start all services
docker compose up -d

# Stop all services
docker compose down

# Restart a specific service
docker compose restart traefik

# View services status
docker ps

# General Traefik logs
docker compose exec traefik tail -f /var/log/traefik/traefik.log | jq .

# Access logs (all requests)
docker compose exec traefik tail -f /var/log/traefik/access.log | jq .

# Follow logs for a specific service
docker compose logs -f example-api
```
