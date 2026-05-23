# rsync — Remote Sync

Fast, versatile, remote (and local) file-copying tool.

```bash
rsync -avz source/ destination/
```

## Options

| Command | Description |
| :--- | :--- |
| `-a` | Archive mode (preserves permissions, times, symbolic links) |
| `-v` | Verbose (show progress) |
| `-z` | Compress file data during the transfer |
| `-P` | Show progress bar and keep partially transferred files |
| `-e ssh` | Use SSH for remote transfer |
| `--delete` | Delete files in destination that no longer exist in source |

## Examples

```bash
# 1. Local copy with progress bar
rsync -avP /src/ /dest/

# 2. Sync to remote server (push)
rsync -avzP local_folder/ user@remote:/path/to/remote_folder/

# 3. Sync from remote server (pull)
rsync -avzP user@remote:/path/to/remote_folder/ local_folder/

# 4. Mirror a directory exactly (WARNING: deletes extra files in destination)
rsync -avP --delete /src/ /dest/
```
