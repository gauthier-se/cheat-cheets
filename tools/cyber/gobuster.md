# gobuster — Directory/DNS/VHost Brute-forcer

Brute-force URIs (directories & files), DNS subdomains, and virtual hosts.

```bash
gobuster dir -u http://example.com -w wordlist.txt
```

## Modes

| Mode | Description |
| :--- | :--- |
| `dir` | Brute-force directories and files |
| `dns` | Brute-force DNS subdomains |
| `vhost` | Brute-force virtual hosts |
| `fuzz` | Fuzz with the `FUZZ` keyword in the URL |
| `s3` | Enumerate open S3 buckets |

## Common Options

| Command | Description |
| :--- | :--- |
| `-u <url>` | Target URL |
| `-w <wordlist>` | Path to the wordlist |
| `-t 50` | Number of concurrent threads |
| `-x php,txt,html` | File extensions to append |
| `-s 200,204,301` | Status codes to show (dir mode) |
| `-b 404` | Status codes to blacklist |
| `-k` | Skip TLS certificate verification |
| `-o out.txt` | Write results to a file |
| `-c "session=abc"` | Send cookies |
| `-H "Authorization: Bearer ..."` | Add a custom header |

## Examples

```bash
# 1. Directory brute-force with extensions
gobuster dir -u http://example.com -w /usr/share/wordlists/dirb/common.txt -x php,html,txt

# 2. More threads and only show interesting codes
gobuster dir -u http://example.com -w wordlist.txt -t 80 -b 404,403

# 3. DNS subdomain enumeration
gobuster dns -d example.com -w subdomains.txt -t 50

# 4. Virtual host discovery
gobuster vhost -u http://example.com -w vhosts.txt --append-domain

# 5. Authenticated scan with a cookie
gobuster dir -u http://example.com -w wordlist.txt -c "PHPSESSID=1a2b3c"
```

## Installation

```bash
brew install gobuster

# Or via Go
go install github.com/OJ/gobuster/v3@latest
```

> Common wordlists live in [SecLists](https://github.com/danielmiessler/SecLists).
