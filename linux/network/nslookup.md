# nslookup — DNS Query

Query Internet name servers interactively.

```bash
nslookup example.com
```

## Examples

```bash
# 1. Get the IP address of a domain
nslookup google.com

# 2. Find the MX (Mail Exchange) records of a domain
nslookup -type=mx google.com

# 3. Query a specific DNS server (e.g., Cloudflare's 1.1.1.1)
nslookup example.com 1.1.1.1
```
