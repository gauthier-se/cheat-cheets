# My Specific Configuration (Neovim)

> [!NOTE]
> Everything listed here is strictly tied to my personal Neovim dotfiles configuration.
> 🔗 **Source code:** [gauthier-se/dotfiles/nvim](https://github.com/gauthier-se/dotfiles/tree/main/nvim/.config/nvim) .

## 1. Windows and Terminals

| Shortcut | Action |
| :--- | :--- |
| `Ctrl + h` | Move focus to the **left** window |
| `Ctrl + j` | Move focus to the **bottom** window |
| `Ctrl + k` | Move focus to the **top** window |
| `Ctrl + l` | Move focus to the **right** window |
| `Esc` + `Esc` (Terminal) | Exit terminal mode (allows returning to normal mode from the integrated terminal) |

## 2. General & UI

| Shortcut | Action |
| :------------------ | :----------------------------------------------------------- |
| `Esc` (Normal mode) | Clear the highlighting from the previous search |
| `<leader>q` | Open the "_Quickfix_" list (listed diagnostics / errors) |

## 3. File Explorer (netrw)

I deliberately use no side file-tree plugin. Files are browsed with the built-in
netrw explorer plus Telescope (`<leader>sf`).

| Shortcut | Action |
| :--- | :--- |
| `<leader>pv` | Open netrw in the current file's directory (`:Ex`) |

Inside netrw: `Enter` open · `-` go up a directory · `%` new file · `d` new dir · `D` delete · `R` rename.

