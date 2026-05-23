# Bash Scripting

Essential syntax and constructs for writing Bash scripts.

## The Shebang

Always start your script with a shebang to ensure it's executed by Bash.

```bash
#!/bin/bash
# Or for better portability:
#!/usr/bin/env bash
```

## Variables

Variables don't have types. **No spaces around the `=` sign!**

```bash
# Definition
NAME="John"
AGE=25

# Usage
echo "Hello, my name is $NAME and I am $AGE years old."
echo "Use braces when concatenating: ${NAME}son"

# Command substitution (saving output to a variable)
CURRENT_DIR=$(pwd)
TODAY=$(date +%Y-%m-%d)
```

## Special Variables

| Variable | Description |
| :--- | :--- |
| `$0` | The name of the script |
| `$1` - `$9` | The first to ninth arguments |
| `$#` | The number of arguments passed |
| `$@` | All arguments passed (as an array) |
| `$?` | The exit status of the last command (0 = success) |
| `$$` | The Process ID (PID) of the current script |
| `$USER` | Current user running the script |

## Conditionals (`if` / `elif` / `else`)

Pay attention to the spaces inside the brackets `[ ]`!

```bash
if [ "$NAME" == "John" ]; then
  echo "Hello John!"
elif [ "$NAME" == "Jane" ]; then
  echo "Hello Jane!"
else
  echo "Who are you?"
fi
```

### Common Conditions

| Condition | True if... |
| :--- | :--- |
| `[ -z "$VAR" ]` | String is empty |
| `[ -n "$VAR" ]` | String is NOT empty |
| `[ "$A" == "$B" ]` | Strings are equal |
| `[ "$A" != "$B" ]` | Strings are NOT equal |
| `[ $A -eq $B ]` | Integers are equal (`-ne` for not equal) |
| `[ $A -gt $B ]` | Integer A is greater than B (`-lt` for less than, `-ge` for greater or equal) |
| `[ -e "file.txt" ]` | File exists |
| `[ -d "dir/" ]` | Directory exists |
| `[ -f "file.txt" ]` | It is a regular file |

## Loops

### For Loop

```bash
# Iterate over a list
for color in red blue green; do
  echo "Color: $color"
done

# Iterate over files in a directory
for file in *.txt; do
  echo "Processing $file"
done

# Standard C-style loop
for ((i=1; i<=5; i++)); do
  echo "Number $i"
done
```

### While Loop

```bash
count=1
while [ $count -le 5 ]; do
  echo "Count: $count"
  ((count++)) # Increment
done
```

## Functions

Functions must be declared before they are called.

```bash
# Definition
greet() {
  local name=$1 # 'local' restricts the variable scope to the function
  echo "Hello, $name!"
}

# Call the function (arguments are passed without parentheses)
greet "Alice"
greet "Bob"
```

## Safety & Debugging

Always use these settings at the top of your scripts to avoid silent failures and bugs (often called the "Bash Strict Mode").

```bash
#!/usr/bin/env bash

# Stop execution immediately if a command fails
set -e

# Treat unset variables as an error
set -u

# Fail if any command in a pipeline fails (not just the last one)
set -o pipefail

# Enable debugging mode (prints each command before executing)
# set -x
```
