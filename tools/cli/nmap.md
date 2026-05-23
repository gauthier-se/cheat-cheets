# nmap — Network Mapper

Network exploration tool and security / port scanner.

```bash
nmap 192.168.1.1
```

## Options

| Command | Description |
| :--- | :--- |
| `-p 80,443` | Scan specific ports |
| `-p-` | Scan all 65535 ports |
| `-sV` | Probe open ports to determine service/version info |
| `-O` | Enable OS detection |
| `-A` | Aggressive scan (OS, version detection, script scanning, traceroute) |
| `-T4` | Faster execution (timing template 0-5) |

## Examples

```bash
# 1. Quick scan of a single IP
nmap 192.168.1.50

# 2. Scan an entire subnet
nmap 192.168.1.0/24

# 3. Scan specific ports with version detection
nmap -p 22,80,443 -sV example.com

# 4. Fast, aggressive scan of a target
nmap -A -T4 example.com
```

## Installation

```bash
brew install nmap
```
