# nikto — Web Server Scanner

Scan web servers for dangerous files, outdated software, and common misconfigurations.

```bash
nikto -h http://example.com
```

## Options

| Command | Description |
| :--- | :--- |
| `-h <host>` | Target host (URL, IP, or hostname) |
| `-p 8080` | Port(s) to scan (comma-separated or range) |
| `-ssl` | Force SSL/TLS on the connection |
| `-Tuning 9` | Restrict tests by type (9 = SQL injection, 1 = interesting files, x = reverse) |
| `-o report.html -Format htm` | Save output to a file in a given format (csv, htm, xml, json) |
| `-useragent "..."` | Set a custom User-Agent |
| `-id user:pass` | HTTP basic auth credentials |
| `-Plugins "apache_expect_xss"` | Run specific plugins |
| `-nointeractive` | Disable interactive prompts (for automation) |

## Examples

```bash
# 1. Basic scan of a host
nikto -h example.com

# 2. Scan a specific port over HTTPS
nikto -h example.com -p 443 -ssl

# 3. Scan multiple ports
nikto -h 192.168.1.10 -p 80,443,8080

# 4. Save a full HTML report
nikto -h example.com -o report.html -Format htm

# 5. Scan behind basic auth
nikto -h example.com -id admin:password

# 6. Tune the scan to only look for injection flaws
nikto -h example.com -Tuning 9
```

## Installation

```bash
brew install nikto

# Or from source
git clone https://github.com/sullo/nikto
perl nikto/program/nikto.pl -h example.com
```
