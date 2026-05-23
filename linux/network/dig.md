# dig — DNS Lookup

Modern replacement for `nslookup`. Extremely detailed DNS querying tool.

```bash
dig example.com
```

## Options

| Command | Description |
| :--- | :--- |
| `+short` | Output only the IP address (short form) |
| `+trace` | Trace the DNS resolution path from root servers |
| `-x <ip>` | Reverse DNS lookup (IP to domain) |
| `@<server>` | Specify a DNS server to query (e.g., `@1.1.1.1`) |

## Examples

```bash
# 1. Get just the IP address
dig +short google.com

# 2. Query specific records (MX, TXT, NS, CNAME)
dig MX google.com
dig TXT google.com

# 3. Query through a specific DNS server (Cloudflare)
dig @1.1.1.1 example.com

# 4. Find the hostname associated with an IP
dig -x 8.8.8.8
```
