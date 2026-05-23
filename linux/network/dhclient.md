# dhclient — DHCP Client

Dynamic Host Configuration Protocol Client. Used to request or release an IP address from a DHCP server.

```bash
sudo dhclient eth0
```

## Options

| Command | Description |
| :--- | :--- |
| `-r` | Release the current IP address |
| `-v` | Verbose mode (shows the DHCP negotiation process) |

## Examples

```bash
# 1. Release the current IP address on interface eth0
sudo dhclient -r eth0

# 2. Request a new IP address for eth0 with verbose output
sudo dhclient -v eth0

# 3. Renew IPs on all interfaces
sudo dhclient
```
