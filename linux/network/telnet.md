# telnet — Network Protocol

Check if a specific port is open on a remote host (very useful for debugging firewalls).

```bash
telnet <host> <port>
```

## Examples

```bash
# 1. Check if a web server is accessible on port 80
telnet example.com 80

# 2. Check if a database is reachable on port 3306
telnet 192.168.1.50 3306

# 3. Quit a telnet session
# Type: Ctrl+] then type: quit
```
