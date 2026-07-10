# Fugitive (Git inside Neovim)

The most complete Git wrapper for Vim (tpope). Replaces lazygit.nvim + diffview in my config.

## My keymaps

| Shortcut | Action |
| :--- | :--- |
| `<leader>gs` | **Git status** (opens the fugitive summary window) |
| `<leader>gb` | **Git blame** (author of each line) |
| `<leader>gd` | **Diff split** of the current file (working tree vs index) |
| `<leader>gl` | **Git log** of the current file (`:Gclog`) |

## Inside the status window (`<leader>gs`)

| Key | Action |
| :--- | :--- |
| `s` | **Stage** the file/hunk under the cursor |
| `u` | **Unstage** the file/hunk |
| `-` | Toggle stage/unstage |
| `=` | Expand/collapse the inline diff |
| `X` | Discard the change under the cursor |
| `cc` | Create a **commit** |
| `ca` | Amend the last commit |
| `dv` | Open the file in a **diff split** |
| `<Enter>` | Open the file under the cursor |
| `gq` / `q` | Close the status window |

## Useful commands

| Command | Action |
| :--- | :--- |
| `:Git` | Git status window |
| `:Git <any git command>` | Run any git command (`:Git push`, `:Git pull`, `:Git rebase -i`) |
| `:Gvdiffsplit` | Vertical diff of the current file against the index |
| `:Gvdiffsplit HEAD~2` | Diff against an arbitrary revision |
| `:Gread` | Revert the buffer to the staged/HEAD version (`git checkout`) |
| `:Gwrite` | Stage the current file (`git add`) |
| `:Gclog` | Load the file's commit history into the quickfix list |
| `:Git blame` | Interactive blame; press `Enter` on a line to view that commit |

> During a merge conflict: `:Gvdiffsplit!` opens a 3-way diff. Use `:diffget //2` (target/ours) and `:diffget //3` (merge/theirs) to pick a side.
