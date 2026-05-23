# curl — Data Transfer

Transfer data from or to a server using various protocols (HTTP, HTTPS, FTP...).

```bash
curl http://example.com
```

## Options

| Command | Description |
| :--- | :--- |
| `-O` | Download file (saves with the remote filename) |
| `-o <file>` | Download file and save it under a custom name |
| `-I` | Fetch only HTTP headers (`HEAD` request) |
| `-L` | Follow HTTP redirects |
| `-X POST` | Specify request method (GET, POST, PUT, DELETE) |
| `-d "<data>"` | Send data in a POST request |
| `-H "<header>"` | Add a custom HTTP header |
| `-s` | Silent mode (hides progress bar) |

## Examples

```bash
# 1. Download a file and follow redirects
curl -L -O https://example.com/file.zip

# 2. Send a POST request with JSON
curl -X POST -H "Content-Type: application/json" -d '{"user":"admin"}' https://api.example.com/login

# 3. View only the response headers
curl -I https://example.com

# 4. Get your public IP address
curl ifconfig.me
```
