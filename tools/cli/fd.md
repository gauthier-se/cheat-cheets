# fd — Search for files

Fast, simple `find` replacement. Respects `.gitignore`.

```bash
fd "config"
```

## Options

| Command | Description |
| :--- | :--- |
| `fd -e json` | By extension (`.json`) |
| `fd -t d "src"` | Directories only |
| `fd -t f "main"` | Files only |
| `fd -H ".env"` | Include hidden files |
| `fd -I` | Include ignored files (`.gitignore`) |
| `fd -E node_modules` | Exclude directory |
| `fd --changed-within 1w`| Modified within 1 week |

## Executing Commands

| Command | Description |
| :--- | :--- |
| `fd -e log -x rm {}` | Run `rm` on each file (N times) |
| `fd -e log -X rm {}` | Run `rm` on all files at once (1 time) |

## Examples

```bash
# 1. Delete all `.DS_Store` files
fd -H "^\.DS_Store$" -x rm

# 2. Convert all MP4s to AVI
fd -e mp4 -x ffmpeg -i {} {}.avi

# 3. Find files modified in last 24h
fd --changed-within 24h

# 4. Python files excluding 'venv'
fd -e py -E venv
```

## Installation

```bash
brew install fd
```
