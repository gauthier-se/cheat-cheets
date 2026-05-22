# fzf — Fuzzy Finder

Interactive fuzzy search for files, history, and processes.

```bash
fzf
```

## Options & Integrations

| Command | Description |
| :--- | :--- |
| `fzf -m` | Multi-selection (use `Tab`) |
| `fzf --preview 'bat --color=always {}'` | Live syntax-highlighted preview |
| `fzf --height 40% --reverse` | Smaller window at bottom, reversed |

## Shortcuts

| Key | Action |
| :--- | :--- |
| `Ctrl+j` / `Ctrl+k` | Navigate down/up |
| `Enter` | Confirm selection |
| `Tab` | Select/Deselect item (`fzf -m` only) |
| `Shift+Tab` | Select and move up |
| `Ctrl+c` / `Esc` | Quit |

## Examples

```bash
# 1. Search and open in Neovim
nvim $(fd -t f | fzf)

# 2. Search history and execute
history | fzf

# 3. Interactive process killer
ps aux | fzf | awk '{print $2}' | xargs kill -9

# 4. Search text interactively (rg + fzf)
rg --line-number --no-heading --color=always "" | fzf --ansi --delimiter : --preview 'bat --color=always {1} --highlight-line {2}'
```

## Installation

```bash
brew install fzf
```
