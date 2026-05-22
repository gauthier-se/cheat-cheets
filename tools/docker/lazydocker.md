# LazyDocker Tutorial

LazyDocker is a terminal user interface (TUI) for Docker and Docker Compose. It provides a visual dashboard to manage your containers, images, volumes, and networks without memorizing complex CLI commands.

## How to Launch LazyDocker?

* **From the terminal:** Run `lazydocker` to open the interface.

---

## Global Navigation

| Key | Action |
| :--- | :--- |
| `x` | Open the contextual menu (shows all options for the selected item) |
| `Esc` / `q` | Go back / Quit LazyDocker |
| `1`, `2`, `3`, `4` | Navigate between the main panels (Project, Containers, Images, Volumes) |
| `Arrow keys` / `h`,`j`,`k`,`l` | Move selection up/down or between panels |
| `Enter` | Focus on the selected item (view detailed logs/stats) |
| `[` / `]` | Navigate between the tabs inside the right panel (Logs, Stats, Config, etc.) |
| `Mouse` | You can click on most elements directly |

---

## Containers Panel

| Key | Action |
| :--- | :--- |
| `s` | **Stop** the selected container |
| `r` | **Restart** the selected container |
| `d` | **Remove** (Delete) the container |
| `e` | **Execute** an interactive shell inside the container (`/bin/sh` or `/bin/bash`) |
| `m` | View the container metrics (CPU/RAM usage in the Stats tab) |
| `c` | Copy the container ID to clipboard |

---

## Images Panel

| Key | Action |
| :--- | :--- |
| `d` | **Remove** (Delete) the selected image |
| `p` | **Prune** unused (dangling) images |

---

## Volumes Panel

| Key | Action |
| :--- | :--- |
| `d` | **Remove** (Delete) the selected volume |
| `p` | **Prune** unused volumes |

---

## Project Panel (Docker Compose)

If you launch `lazydocker` inside a directory with a `docker-compose.yml`, this panel allows you to manage the entire stack at once.

| Key | Action |
| :--- | :--- |
| `e` | Edit the `docker-compose.yml` file |
| `d` | **Down**: Stop and remove all containers in the project |
| `u` | **Up**: Create and start the project |
| `r` | **Restart** all services |

---

## Installation

```bash
brew install jesseduffield/lazydocker/lazydocker
```
