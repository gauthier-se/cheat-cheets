# Linux / Shell Tips

Built-in shell commands that are often underutilized.

---

## Navigation

### `cd -` — Return to previous directory

Switches between the current directory and the last visited directory. Acts like the "back" button of a browser.

```bash
cd ~/Projects
cd /tmp
cd -        # returns to ~/Projects
cd -        # returns to /tmp
```

### `cd` (without arguments) — Return to home

Shortcut for `cd ~`. Returns directly to the home directory.

```bash
cd          # equivalent to cd ~
```

---

## Information

### `whereis` — Locate binary, source, and manual page files

Unlike `which` that only provides the binary path, `whereis` also searches for manual pages and source files.

```bash
whereis git
# git: /usr/bin/git /usr/share/man/man1/git.1

whereis python3
# python3: /usr/bin/python3 /usr/lib/python3 /usr/share/man/man1/python3.1

# Binary only
whereis -b git

# Documentation only
whereis -m git
```

### `whatis` — Display one-line manual page descriptions

Displays a short description of a command (the first line of its man page). Faster than `man`.

```bash
whatis curl
# curl (1) - transfer a URL

whatis ls grep tar
# ls (1)   - list directory contents
# grep (1) - print lines that match patterns
# tar (1)  - an archiving utility
```

### `type` — Indicate how a command would be interpreted

Indicates whether a command is an alias, a function, a builtin, or a binary file.

```bash
type ls
# ls is an alias for ls --color=auto

type cd
# cd is a shell builtin

type git
# git is /usr/bin/git
```

---

## Aliases

### `alias` — Create command shortcuts

Displays or creates aliases for long commands.

```bash
# List all defined aliases
alias

# Create a temporary alias (current session only)
alias ll="ls -la"
alias gs="git status"
alias dc="docker compose"

# Remove an alias
unalias ll
```

> [!TIP] Personal Configuration
> For permanent aliases, add them to your `~/.zshrc`:
> ```bash
> alias lg="lazygit"
> alias vim="nvim"
> ```

---

## History and Recall

### `!!` — Repeat the last command

```bash
apt install vim       # Permission denied
sudo !!               # executes: sudo apt install vim
```

### `!$` — Last argument of the previous command

```bash
mkdir -p ~/Projects/new
cd !$                 # executes: cd ~/Projects/new
```

### `!*` — All arguments of the previous command

```bash
echo one two three
cat !*                # executes: cat one two three
```

---

## Miscellaneous

### `command -v` — Check if a command exists

Portable alternative to `which`, highly useful in shell scripts.

```bash
command -v docker && echo "Docker installed" || echo "Docker missing"
```

### `fc` — Edit the last command in an editor

Opens the last command in your `$EDITOR` so you can modify it before running it again.

```bash
fc        # opens the last command in nvim/vim
```

### `reset` — Reset the terminal

Use this when the terminal is broken (unreadable characters, no line breaks, etc.).

```bash
reset     # restores the terminal to a clean state
```

### `watch` — Execute a command periodically

Runs a command every N seconds and displays the output.

```bash
# Watch files every 2 seconds
watch ls -la

# Every 5 seconds, highlighting differences
watch -n 5 -d "docker ps"

# Monitor disk usage
watch df -h
```
