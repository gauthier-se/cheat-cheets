# iptables — Firewall

Administration tool for IPv4 packet filtering and NAT. (Often replaced by `nftables` or wrapped by `ufw`/`firewalld`, but still essential to know).

```bash
sudo iptables -L
```

## Options

| Command | Description |
| :--- | :--- |
| `-L` | List rules |
| `-S` | List rules in a script-friendly format |
| `-F` | Flush (delete) all rules |
| `-A <chain>` | Append a rule to a chain (INPUT, OUTPUT, FORWARD) |
| `-I <chain> 1` | Insert a rule at the top of a chain |
| `-D <chain> 1` | Delete rule number 1 from a chain |
| `-p <protocol>`| Specify protocol (`tcp`, `udp`, `icmp`) |
| `--dport <port>`| Specify destination port |
| `-j <target>` | Action to take (`ACCEPT`, `DROP`, `REJECT`) |

## Examples

```bash
# 1. List all current rules with line numbers
sudo iptables -L -n -v --line-numbers

# 2. Allow incoming SSH (port 22)
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# 3. Block a specific IP address
sudo iptables -A INPUT -s 123.45.67.89 -j DROP

# 4. Delete the first rule in the INPUT chain
sudo iptables -D INPUT 1

# 5. Save rules permanently (Debian/Ubuntu)
sudo iptables-save > /etc/iptables/rules.v4
```
