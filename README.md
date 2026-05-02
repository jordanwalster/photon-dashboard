# Photon Screenshot Dashboard

![Photon Logo](/logo.png)

![Version](https://img.shields.io/badge/version-v1.0.3-success)
![Docker](https://img.shields.io/badge/docker-grey?logo=docker)

A modern, self-hosted PHP screenshot and media management dashboard with powerful organization features, sharing capabilities, and a clean web interface.

The project consists of three main components:

1. **Photon Dashboard** (`photon`): Web interface for managing screenshots.
2. **Photon Worker** (`worker`): Background processes (OCR and thumbnail generation).
3. **MariaDB Database** (`db`): Stores metadata and application data.

Keep up-to-date on new releases by following the [changelog](./changelog.md).

## Features

- **Smart Organization**: Organize screenshots with folders and tags.
- **Advanced Search**: Find images quickly by name or content using OCR.
- **Easy Sharing**: Built-in public sharing URLs.
- **Media Support**: JPG, PNG, GIF, and MP4 (experimental) file support.
- **Bulk Operations**: Select and manage multiple files at once.
- **Sorting Options**: Sort by date, size, or filename.
- **Trash Management**: Safe deletion with trash functionality.
- **Background Processing**: Dedicated worker for compression and OCR processing.
- **Database Storage**: MariaDB backend for reliable data persistence.

An external authentication proxy is recommended to protect your dashboard from unwanted eyes.

## Quick Start

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd photon-dashboard
   ```

2. **Configure environment**
   ```bash
   cp .env.example .env
   # Edit .env with your settings
   ```

3. **Create data directory**
   ```bash
   mkdir data
   # Copy your screenshots to ./data/
   ```

4. **Deploy with Docker Compose**
   ```bash
   docker-compose -f examples/compose-default.yml up -d
   ```

5. **Access the dashboard**
   - Open http://localhost:8090 in your browser

## Configuration

### Deployment Options

#### Standard Deployment
Use `examples/compose-default.yml` for simple deployments:
```bash
docker-compose -f examples/compose-default.yml up -d
```

#### Traefik – Custom Domains
Use `examples/compose-traefik.yml` for reverse proxy setups, authentication and custom domains. 

## Project Structure

```
photon-dashboard/
├── examples/
│   ├── compose-default.yml    # Default example for basic usage.
│   ├── compose-traefik.yml    # Traefik example for custom domain routing.
│   └── .env.example           # Environment configuration
│
└── changelog.md               # Version history
```

## Updates

Container images are available at:
- Dashboard: `git.jrdn.dev/photon/photon-dashboard:latest`
- Worker: `git.jrdn.dev/photon/photon-worker:latest`

View version history: [Container Registry](https://git.jrdn.dev/jordanwalster/-/packages/container/photon-dashboard/versions)

### Logs
```bash
# View photon logs
docker logs photon_dashboard

# View worker logs  
docker logs photon_worker

# View database logs
docker logs photon_db
```
