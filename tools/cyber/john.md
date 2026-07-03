# john — John the Ripper Password Cracker

Crack password hashes via dictionary, incremental (brute-force), and rule-based attacks.

```bash
john --wordlist=rockyou.txt hashes.txt
```

## Options

| Command | Description |
| :--- | :--- |
| `--wordlist=<file>` | Dictionary attack with a wordlist |
| `--rules` | Apply mangling rules to the wordlist |
| `--incremental` | Brute-force mode |
| `--format=<name>` | Force a hash format (e.g. `raw-md5`, `nt`, `sha512crypt`) |
| `--show hashes.txt` | Show already-cracked passwords |
| `--session=name` | Name a session (for resuming) |
| `--restore=name` | Resume a saved session |
| `--fork=4` | Use multiple CPU cores |
| `--list=formats` | List all supported hash formats |
| `--pot=custom.pot` | Use a custom pot (cracked) file |

## The `*2john` Helpers

Convert files into a crackable hash format:

```bash
zip2john secret.zip > hash.txt
rar2john secret.rar > hash.txt
ssh2john id_rsa       > hash.txt
pdf2john document.pdf > hash.txt
```

## Examples

```bash
# 1. Straight dictionary attack
john --wordlist=rockyou.txt hashes.txt

# 2. Dictionary + mangling rules
john --wordlist=rockyou.txt --rules hashes.txt

# 3. Force a format when auto-detect is wrong
john --format=raw-md5 --wordlist=rockyou.txt hashes.txt

# 4. Show what has been cracked
john --show hashes.txt

# 5. Brute-force with all cores
john --incremental --fork=4 hashes.txt

# 6. Crack a password-protected zip
zip2john secret.zip > zip.hash
john --wordlist=rockyou.txt zip.hash
```

## Installation

```bash
# Community-enhanced "jumbo" version (recommended, has all *2john tools)
brew install john-jumbo
```
