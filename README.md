# Docker Stremio Server

Self-hosted Stremio streaming server using Docker.

## Description

Deploy your own Stremio streaming server for media content aggregation and streaming. This setup provides a containerized environment for the official Stremio server.

## Prerequisites

- Docker
- Docker Compose

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/docker-stremio.git
cd docker-stremio

# Start the server
docker-compose up -d
```

## Configuration

### Ports

| Port | Description |
|------|-------------|
| 11470 | Local API |
| 12470 | External API |

### Environment Variables

Create a `.env` file if you need custom configuration:

```bash
cp .env.example .env
# Edit .env with your settings
```

## Usage

Once started, access:
- Local API: `http://localhost:11470`
- External API: `http://localhost:12470`

Configure your Stremio client to use this server address.

## Docker Compose

```yaml
version: "3.9"

services:
  stremio:
    image: stremio/server:latest
    container_name: stremio-server
    restart: unless-stopped
    ports:
      - "11470:11470"
      - "12470:12470"
```

## Commands

```bash
# Start
docker-compose up -d

# Stop
docker-compose down

# View logs
docker-compose logs -f stremio

# Restart
docker-compose restart
```

## Troubleshooting

### Port conflicts
If ports are in use, modify the port mappings in `compose.yml`.

### Container not starting
```bash
docker-compose logs stremio
```

## Resources

- [Stremio Official](https://www.stremio.com/)
- [Stremio GitHub](https://github.com/Stremio)

## License

MIT License - See LICENSE file for details.

---

**Note**: This is a personal deployment configuration. Ensure compliance with content licensing in your jurisdiction.
