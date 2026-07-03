# ffuf — Fast Web Fuzzer

Blazing-fast web fuzzer written in Go. Use the `FUZZ` keyword anywhere in the request.

```bash
ffuf -u http://example.com/FUZZ -w wordlist.txt
```

## Options

| Command | Description |
| :--- | :--- |
| `-u <url>` | Target URL with a `FUZZ` marker |
| `-w <wordlist>` | Wordlist (`-w list.txt:KEYWORD` to rename the keyword) |
| `-t 40` | Concurrent threads |
| `-e .php,.html` | Extensions to append |
| `-mc 200,301` | Match HTTP status codes |
| `-fc 404` | Filter out status codes |
| `-fs 4242` | Filter out responses by size |
| `-fw 12` | Filter out by word count |
| `-X POST -d "..."` | Method and POST body |
| `-H "Header: val"` | Add a header (repeatable) |
| `-recursion` | Recurse into found directories |
| `-o out.json -of json` | Output to file/format |
| `-c` | Colorized output |

## Examples

```bash
# 1. Directory discovery
ffuf -u http://example.com/FUZZ -w common.txt -c

# 2. Find files with extensions, hide 404s
ffuf -u http://example.com/FUZZ -w words.txt -e .php,.txt -fc 404

# 3. Virtual host fuzzing
ffuf -u http://example.com -H "Host: FUZZ.example.com" -w subs.txt -fs 4242

# 4. POST parameter fuzzing (filter noise by response size)
ffuf -u http://example.com/login -X POST \
  -d "user=admin&pass=FUZZ" -w rockyou.txt -fs 1500

# 5. Recursive scan with two wordlists
ffuf -u http://example.com/W1/W2 -w dirs.txt:W1 -w files.txt:W2 -recursion
```

## Installation

```bash
brew install ffuf

# Or via Go
go install github.com/ffuf/ffuf/v2@latest
```
