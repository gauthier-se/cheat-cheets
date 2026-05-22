# Docker Compose Commands

## Lifecycle Management

| Command | Description |
| :--- | :--- |
| `docker compose up -d` | Create and start containers in the background (detached mode) |
| `docker compose down` | Stop and remove containers, networks, and default volumes |
| `docker compose down -v` | Also remove named volumes declared in the `volumes` section |
| `docker compose start` | Start existing containers without recreating them |
| `docker compose stop` | Stop running containers without removing them |
| `docker compose restart` | Restart all services |

## Inspection and Logs

| Command | Description |
| :--- | :--- |
| `docker compose ps` | List running containers for the current project |
| `docker compose logs -f` | Follow live logs for all services |
| `docker compose logs -f <service>` | Follow live logs for a specific service |

## Building and Executing

| Command | Description |
| :--- | :--- |
| `docker compose build` | Build or rebuild services |
| `docker compose up -d --build` | Force rebuild of images before starting containers |
| `docker compose exec <service> sh` | Execute a shell inside a running service container |
| `docker compose run --rm <service> sh`| Run a one-off command in a new container and remove it after exit |
