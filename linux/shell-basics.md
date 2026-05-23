# Shell Basics & Expansions

Essential shell syntax for redirection, chaining, and quick expansions.

## Redirection & Piping

| Syntax | Action |
| :--- | :--- |
| `>` | Redirect output to a file (overwrites existing content) |
| `>>` | Append output to the end of a file |
| `<` | Read input from a file |
| `2>` | Redirect error output (stderr) to a file |
| `2>&1` | Redirect stderr to standard output (stdout) |
| `/dev/null`| The "black hole". Discard output (e.g., `> /dev/null`) |
| `\|` | Pipe the output of one command as input to the next |

**Examples:**
```bash
# Save the list of files to a text file
ls -la > files.txt

# Add a line to the end of a file
echo "New line" >> files.txt

# Discard annoying error messages
find / -name "config" 2> /dev/null
```

## Command Chaining

| Syntax | Action |
| :--- | :--- |
| `;` | Execute commands sequentially (regardless of success) |
| `&&` | Execute the next command **only if** the previous one succeeded |
| `\|\|` | Execute the next command **only if** the previous one failed |

**Examples:**
```bash
# Build the project, and IF successful, restart the service
make build && systemctl restart my-service

# Create directory, if it fails print an error
mkdir /root/test || echo "You need sudo permissions!"
```

## Brace Expansion `{}`

Brace expansion is a powerful way to generate arbitrary strings, especially useful for creating multiple files or directories at once.

**Examples:**
```bash
# Create files from 1 to 10 (file1.txt, file2.txt ... file10.txt)
touch file{1..10}.txt

# Zero-padded numbers (file01.txt, file02.txt ... file10.txt)
touch file{01..10}.txt

# Create a full directory structure instantly
mkdir -p src/{components,utils,hooks,assets/images}

# Backup a file quickly (copies config.yml to config.yml.bak)
cp config.yml{,.bak}

# Create alphabet ranges
echo {a..z}
```

## Wildcards (Globbing)

Used to select multiple files at once based on pattern matching.

| Wildcard | Description |
| :--- | :--- |
| `*` | Matches **any** number of characters (including none) |
| `?` | Matches exactly **one** single character |
| `[abc]` | Matches any **one** character from the enclosed list |
| `[a-z]` | Matches any **one** character in the range |
| `[^abc]` | Matches any character **NOT** in the list |

**Examples:**
```bash
# Move all .jpg files to the images folder
mv *.jpg images/

# Delete files like temp1.log, temp2.log, etc. (but NOT temp12.log)
rm temp?.log

# List all files starting with 'a', 'b', or 'c'
ls [abc]*

# Copy all files EXCEPT those starting with 'test'
# Note: Requires extended globbing enabled (`shopt -s extglob`)
cp !(test*) backup/
```
