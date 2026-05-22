# HTTPie (http) — HTTP Client

Modern, user-friendly `curl` replacement. JSON support built-in, syntax highlighting.

```bash
http api.example.com
```

## Options

| Command | Description |
| :--- | :--- |
| `http -f` | Send as form-encoded (`application/x-www-form-urlencoded`) |
| `http -d` / `--download` | Download a file (like `wget`) |
| `http -h` / `--headers` | Print only the HTTP headers (no body) |
| `http -b` / `--body` | Print only the response body (no headers) |
| `http --session=NAME` | Create/use a session (saves cookies/auth) |
| `http -A bearer -a TOKEN` | Use Bearer Token auth |
| `http -a user:pass` | Basic HTTP Auth |

## Examples

```bash
# 1. POST JSON data (defaults to application/json)
# Note: '=' is for strings, ':=' is for raw JSON types (numbers, booleans)
http POST api.example.com/users name="John Doe" age:=30 isActive:=true

# 2. Authenticate with a JWT (Bearer Token)
# Via custom header:
http api.example.com/protected "Authorization: Bearer <your_jwt_here>"
# Or via built-in auth flag:
http -A bearer -a <your_jwt_here> api.example.com/protected

# 3. Send JSON payload from a local file
http POST api.example.com/upload < data.json

# 4. Maintain a persistent session (Keep Cookies & Auth state)
http --session=dev -a user:pass api.example.com/login
http --session=dev api.example.com/profile

# 5. Send Query Parameters (using '==')
http api.example.com/search q==httpie page==2
```

## Installation

```bash
brew install httpie
```
