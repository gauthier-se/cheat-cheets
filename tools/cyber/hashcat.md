# hashcat — GPU Password Cracker

The fastest password recovery tool, leveraging GPUs for hashes of every kind.

```bash
hashcat -m 0 -a 0 hashes.txt rockyou.txt
```

## Core Flags

| Command | Description |
| :--- | :--- |
| `-m <id>` | Hash type (see below) |
| `-a <id>` | Attack mode |
| `-o cracked.txt` | Write results to a file |
| `--show` | Show already-cracked hashes |
| `-r rules/best64.rule` | Apply a rules file |
| `-w 3` | Workload profile (1-4, higher = more GPU) |
| `--force` | Ignore warnings |
| `--session=name` / `--restore` | Save / resume a session |
| `--status` | Show live status |

## Attack Modes (`-a`)

| ID | Mode |
| :--- | :--- |
| `0` | Straight (dictionary) |
| `1` | Combination (two wordlists) |
| `3` | Brute-force / mask |
| `6` | Hybrid wordlist + mask |
| `7` | Hybrid mask + wordlist |

## Common Hash Types (`-m`)

| ID | Type |
| :--- | :--- |
| `0` | MD5 |
| `100` | SHA1 |
| `1400` | SHA-256 |
| `1000` | NTLM |
| `1800` | sha512crypt (Linux) |
| `3200` | bcrypt |
| `2500` | WPA/WPA2 (legacy) |
| `22000` | WPA-PBKDF2/PMKID (modern) |

> Run `hashcat --example-hashes` or check the [wiki](https://hashcat.net/wiki/doku.php?id=example_hashes) to identify a mode.

## Mask Charsets (`-a 3`)

`?l` lower · `?u` upper · `?d` digit · `?s` special · `?a` all · `?h`/`?H` hex

## Examples

```bash
# 1. Dictionary attack on MD5
hashcat -m 0 -a 0 hashes.txt rockyou.txt

# 2. Dictionary + rules (huge multiplier)
hashcat -m 1000 -a 0 ntlm.txt rockyou.txt -r rules/best64.rule

# 3. Brute-force all 8-char lowercase
hashcat -m 0 -a 3 hashes.txt ?l?l?l?l?l?l?l?l

# 4. Mask: known prefix "Pass" + 4 digits
hashcat -m 0 -a 3 hashes.txt Pass?d?d?d?d

# 5. Crack WPA2 handshake
hashcat -m 22000 -a 0 capture.hc22000 rockyou.txt

# 6. Show cracked results
hashcat -m 0 hashes.txt --show
```

## Installation

```bash
brew install hashcat
```
