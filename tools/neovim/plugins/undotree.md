# Undotree (Undo history visualizer)

Neovim keeps undo history as a *tree*, not a linear stack: if you undo and then type,
the old future isn't lost — it becomes a separate branch. Undotree lets you see and
navigate that tree.

## My keymap

| Shortcut | Action |
| :--- | :--- |
| `<leader>u` | Toggle the Undotree panel |

## Inside the Undotree panel

| Key | Action |
| :--- | :--- |
| `j` / `k` | Move to the next / previous state (older / newer) |
| `<Enter>` | Restore the selected state |
| `p` | Preview the diff of the state under the cursor |
| `J` / `K` | Jump between saved-file (write) states |
| `q` | Close the panel |

> Works best with a persistent undo file (`vim.o.undofile = true`, already set in my config),
> so the history survives even after closing and reopening a file.
