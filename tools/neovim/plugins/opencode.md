# OpenCode (AI Assistant)

> [!NOTE]
> Everything listed here is strictly tied to my personal Neovim dotfiles configuration.
> 🔗 **Source code:** [gauthier-se/dotfiles/nvim](https://github.com/gauthier-se/dotfiles/tree/main/nvim/.config/nvim) .

| Shortcut | Action |
| :--- | :--- |
| `Ctrl + a` | **Ask opencode** a question |
| `Ctrl + x` | **Execute** an action / Show picker |
| `Ctrl + .` | **Toggle** the OpenCode window |
| `go` | Send **selection/motion** to OpenCode |
| `goo` | Send **current line** to OpenCode |
| `+` | Increment number (replaces default `Ctrl+a`) |
| `-` | Decrement number (replaces default `Ctrl+x`) |

## Context Placeholders

| Placeholder | Context sent to the AI |
| :--- | :--- |
| `@this` | Current buffer or visual selection |
| `@buffer` | Full content of the buffer |
| `@buffers` | All open buffers |
| `@visible` | What is visible on screen |
| `@diagnostics` | LSP errors / warnings |
| `@diff` | Current Git diff |
| `@quickfix` | Quickfix list content |

## Predefined Actions (`Ctrl + x`)

| Action | Description |
| :--- | :--- |
| `review` | Code review |
| `explain` | Explain code |
| `fix` | Fix errors |
| `optimize` | Optimize code |
| `document` | Generate documentation |
| `test` | Generate tests |
| `implement` | Implement code |
