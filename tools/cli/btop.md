# btop — System Monitor

Rich `top`/`htop` replacement (CPU, RAM, disks, network).

```bash
btop
```

## Options

| Command | Description |
| :--- | :--- |
| `btop --utf-force` | Force UTF-8 (fixes rendering) |
| `btop -p <id>` | Start with preset (0-4) |
| `btop --update 500` | Update interval in ms |

## Shortcuts

| Key | Action |
| :--- | :--- |
| `m` | Menu / Config |
| `1`-`4` | Switch view presets |
| `f` | Filter processes |
| `e` | Process tree view |
| `k` | Kill selected process |
| `+` / `-` | Zoom selected process |
| `Arrows` | Navigate processes |

## Examples

* **Kill hogs**: Press `f` to filter, arrows to select, `k` to kill.
* **Disk I/O**: Preset `2` for read/write speeds.
* **Network**: Graph auto-scales for bandwidth usage.

## Installation

```bash
brew install btop
```
