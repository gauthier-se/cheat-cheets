# ping — Network Testing

Test reachability of a host on an IP network.

```bash
ping google.com
```

## Options

| Command | Description |
| :--- | :--- |
| `-c 4` | Stop after sending 4 packets |
| `-i 2` | Wait 2 seconds between each packet |
| `-s 1000` | Specify packet size (bytes) |

## Examples

```bash
# 1. Ping a host 4 times and stop
ping -c 4 8.8.8.8

# 2. Continuous ping (press Ctrl+C to stop)
ping 1.1.1.1
```
