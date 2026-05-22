# rg (ripgrep) — Search inside files

Fast `grep` replacement. Respects `.gitignore`.

```bash
rg "TODO"
```

## Options

| Command | Description |
| :--- | :--- |
| `rg -i "error"` | Ignore case |
| `rg -w "word"` | Exact word match |
| `rg -v "debug"` | Invert match (exclude pattern) |
| `rg -C 2 "panic"` | Show 2 lines context (before & after) |
| `rg -A 3 -B 1 "panic"` | Show 3 lines **A**fter, 1 line **B**efore |
| `rg "func main" -t go` | Search in Go files only |
| `rg -c "import"` | Count occurrences per file |
| `rg -l "TODO"` | List matching filenames only |
| `rg --hidden ".env"` | Include hidden files |

## Examples

```bash
# 1. Search function across codebase
rg "def get_user"

# 2. Find IPs in logs (Regex)
rg "\b\d{1,3}(\.\d{1,3}){3}\b" /var/log/

# 3. Files containing BOTH "error" and "timeout"
rg -l "error" | xargs rg "timeout"

# 4. Replace text across files
rg -l "old_var" | xargs sed -i '' 's/old_var/new_var/g'
```

## Installation

```bash
brew install ripgrep
```
