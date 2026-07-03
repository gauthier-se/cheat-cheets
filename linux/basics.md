# Linux Basics

Essential Linux commands for daily usage, along with their most useful flags.

## Directory & File Navigation

| Command | Description |
| :--- | :--- |
| `pwd` | Print Working Directory (where am I?) |
| `ls -la` | List all files (`-a` for hidden) in long format (`-l`) |
| `ls -lh` | List files with human-readable sizes (`-h`) |
| `ls -lt` | List files sorted by modification time (newest first) |
| `tree -L 2` | Show directory structure as a tree (up to 2 levels deep) |

## File Operations

| Command | Description |
| :--- | :--- |
| `cp -r <src> <dest>` | Copy recursively (for directories) |
| `cp -i <src> <dest>` | Interactive copy (prompts before overwriting) |
| `mv <src> <dest>` | Move or rename a file/directory |
| `rm -rf <dir>` | Remove directory recursively (`-r`) and forcefully (`-f`) |
| `mkdir -p a/b/c` | Create intermediate directories as required (`-p`) |
| `touch <file>` | Create an empty file or update its timestamp |

## Viewing File Content

| Command | Description |
| :--- | :--- |
| `cat -n <file>` | Display file contents with line numbers (`-n`) |
| `less -S <file>`| View file with horizontal scrolling for long lines (`-S`) |
| `tail -f <file>`| Follow file content in real-time (great for logs) |
| `tail -n 100 <file>`| View the last 100 lines of a file |
| `head -n 20 <file>` | View the first 20 lines of a file |

## Permissions & Ownership

### Numeric Permissions

Permissions are calculated by adding these values together for the Owner, Group, and Others:

| Value | Permission | Description |
| :---: | :--- | :--- |
| `4` | Read (`r`) | Can read the file / list the directory |
| `2` | Write (`w`) | Can modify the file / add or delete files in the directory |
| `1` | Execute (`x`) | Can execute the file / enter the directory |
| `0` | None (`-`) | No permissions |

*Example:* `755` = `7` (Owner: 4+2+1) + `5` (Group: 4+1) + `5` (Others: 4+1)

### Commands

| Command | Description |
| :--- | :--- |
| `chmod +x <script>` | Make a file executable |
| `chmod 755 <dir>` | Read/Execute for everyone, Write only for owner |
| `chmod 644 <file>` | Read/Write for owner, Read-only for everyone else |
| `chmod 600 <key>` | Read/Write only for owner (essential for SSH keys) |
| `chown user:group <file>` | Change the owner and group of a file |
| `chown -R user:group <dir>`| Change ownership recursively for a directory |

## Archiving & Compression

| Command | Description |
| :--- | :--- |
| `tar -czvf arc.tar.gz folder/` | Create (`-c`) a GZip (`-z`) archive, verbose (`-v`) |
| `tar -xzvf arc.tar.gz` | Extract (`-x`) a GZip archive |
| `zip -r arc.zip folder/` | Create a zip archive recursively |
| `unzip arc.zip` | Extract a zip archive |

## System Info & Resources

| Command | Description |
| :--- | :--- |
| `df -h` | View disk space usage in human-readable format |
| `du -sh <folder>` | Calculate total size of a specific folder |
| `free -m` | View available RAM in Megabytes |
| `uname -a` | Print all system information (kernel version, architecture) |
| `history` | List previously executed commands |
| `uptime` | Show how long the system has been running |

## Processes

| Command | Description |
| :--- | :--- |
| `ps aux` | List all running processes for all users |
| `kill -9 <PID>` | Force kill a process by its ID |
| `killall <name>` | Kill all processes matching a specific name |
