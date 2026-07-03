# hydra — Network Login Brute-forcer

Fast parallel login cracker supporting many protocols (SSH, FTP, HTTP, RDP, SMB…).

```bash
hydra -l admin -P passwords.txt ssh://192.168.1.10
```

## Options

| Command | Description |
| :--- | :--- |
| `-l <user>` | Single username |
| `-L <file>` | Username list |
| `-p <pass>` | Single password |
| `-P <file>` | Password list |
| `-C user:pass.txt` | Colon-separated combo list |
| `-s <port>` | Non-default port |
| `-t 16` | Parallel tasks (threads) |
| `-f` | Stop after the first valid pair found |
| `-V` | Verbose (show every attempt) |
| `-o found.txt` | Write found credentials to a file |
| `-e nsr` | Try null (`n`), same-as-login (`s`), reversed (`r`) |

## Protocol Syntax

```
hydra [options] <target> <service>
hydra [options] <service>://<target>[:port][/opts]
```

## Examples

```bash
# 1. Brute-force SSH with a single user
hydra -l root -P rockyou.txt ssh://192.168.1.10

# 2. FTP with user and password lists, stop on first hit
hydra -L users.txt -P pass.txt -f ftp://10.0.0.5

# 3. HTTP POST form (fail string after the last colon)
hydra -l admin -P pass.txt example.com http-post-form \
  "/login:user=^USER^&pass=^PASS^:Invalid credentials"

# 4. HTTP basic auth on a custom port
hydra -L users.txt -P pass.txt -s 8080 example.com http-get /admin

# 5. RDP with more threads and verbose output
hydra -l administrator -P pass.txt -t 4 -V rdp://192.168.1.20
```

> HTTP form placeholders: `^USER^` and `^PASS^` are substituted per attempt. The 3rd colon field is the *failure* condition string.

## Installation

```bash
brew install hydra
```
