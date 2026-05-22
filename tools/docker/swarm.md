# Docker Swarm Commands

## Cluster Management

| Command | Description |
| :--- | :--- |
| `docker swarm init` | Initialize a new swarm (makes current node a manager) |
| `docker swarm join-token worker` | Display the command and token needed to join as a worker |
| `docker swarm join-token manager`| Display the command and token needed to join as a manager |
| `docker swarm leave --force` | Leave the swarm |
| `docker node ls` | List all nodes in the swarm (manager only) |
| `docker node promote <node>` | Promote a worker node to manager |

## Services Management

| Command | Description |
| :--- | :--- |
| `docker service create --name <name> -p 80:80 <image>` | Create a new service |
| `docker service ls` | List all running services |
| `docker service ps <name>` | List the tasks (containers) of a specific service |
| `docker service scale <name>=5` | Scale a service to 5 replicas |
| `docker service update --image <new_image> <name>` | Update the image of a running service |
| `docker service logs -f <name>` | Follow logs of a service |
| `docker service rm <name>` | Remove a service |

## Stacks (Compose for Swarm)

| Command | Description |
| :--- | :--- |
| `docker stack deploy -c docker-compose.yml <stack_name>` | Deploy a new stack or update an existing one |
| `docker stack ls` | List all deployed stacks |
| `docker stack services <stack_name>` | List services in a specific stack |
| `docker stack rm <stack_name>` | Remove a stack |
