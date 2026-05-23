# Yazi

A blazing fast terminal file manager written in Rust, based on async I/O.

## Navigation

| Keybinding | Description |
| :--- | :--- |
| `h`, `j`, `k`, `l` | Move Left, Down, Up, Right (Vim style) |
| `<Arrow Keys>` | Move around |
| `g`, `g` / `G` | Go to the top / Go to the bottom |
| `<Space>` | Toggle selection of the hovered file |
| `v` | Enter Visual mode (select multiple files) |
| `V` | Enter Visual mode (select all) |
| `<Enter>` | Open the hovered file/directory |
| `Z` | Jump to a directory using Zoxide (if integrated) |

## File Operations

| Keybinding | Description |
| :--- | :--- |
| `y` | Yank (copy) the selected files |
| `x` | Cut the selected files |
| `p` | Paste the yanked/cut files |
| `d` | Trash the selected files |
| `D` | Permanently delete the selected files |
| `a` | Create a new file or directory (add `/` at the end for directory) |
| `r` | Rename the hovered file |
| `c` | Change file permissions (chmod) |

## Search & Filter

| Keybinding | Description |
| :--- | :--- |
| `f` | Find files matching a char (jump to next) |
| `F` | Find files matching a char (jump to previous) |
| `/` | Search files via regex |
| `s` | Filter files in the current directory |
| `S` | Search files globally using `fd` or `rg` |

## Tabs & View

| Keybinding | Description |
| :--- | :--- |
| `t` | Create a new tab |
| `1` - `9` | Switch to tab by number |
| `[`, `]` | Switch to previous/next tab |
| `q` | Quit the application |
| `~` | Open the help menu / keybinds list |

## Configuration

Yazi is highly customizable. The configuration files are usually located in `~/.config/yazi/` :
- `yazi.toml` : General settings, layout, plugins.
- `keymap.toml` : Custom keybindings.
- `theme.toml` : Colors and styling.
