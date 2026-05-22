# Docker Basic Commands

## Image Management

| Command | Description |
| :--- | :--- |
| `docker pull <image>` | Download an image from Docker Hub |
| `docker images` | List all local images |
| `docker rmi <image>` | Delete an image |
| `docker build -t <name> .` | Build an image from a Dockerfile in the current directory |
| `docker image prune` | Remove unused (dangling) images |

## Container Management

| Command | Description |
| :--- | :--- |
| `docker run <image>` | Create and start a container |
| `docker run -d -p 80:80 <image>` | Run detached (`-d`) and map port 80 to 80 |
| `docker run -it <image> sh` | Run interactively (`-i`) with a terminal (`-t`) |
| `docker ps` | List running containers |
| `docker ps -a` | List all containers (running and stopped) |
| `docker stop <container>` | Gracefully stop a running container |
| `docker start <container>` | Start a stopped container |
| `docker rm <container>` | Remove a stopped container |
| `docker rm -f <container>` | Force remove a running container |
| `docker logs -f <container>` | Follow live logs of a container |
| `docker exec -it <container> sh` | Execute an interactive shell inside a running container |

## System & Cleanup

| Command | Description |
| :--- | :--- |
| `docker system df` | Show docker disk usage |
| `docker system prune -a` | Remove all unused containers, networks, images, and volumes |
