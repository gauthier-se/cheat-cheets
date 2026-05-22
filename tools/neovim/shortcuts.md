# Neovim Shortcuts (Kickstart.nvim)

Here is a list of the most useful shortcuts for my current Neovim configuration.

> [!NOTE]
> **Generic:** Most basic editing commands and text objects listed in sections 1 to 3 are standard Vim/Neovim features.
> 
> **Personal:** My Leader key (`<leader>`) is configured to the Space bar (`<space>`). All shortcuts starting with `Space`, as well as Telescope, LSP, and Git integrations, are specific to my personal Kickstart.nvim-based configuration. 
> 🔗 **Source code:** [gauthier-se/dotfiles/nvim](https://github.com/gauthier-se/dotfiles/tree/main/nvim/.config/nvim) .


---

## 1. Basic Editing (Standard Vim)

| Shortcut   | Action                                        | VSCode Equivalent                |
| ---------- | --------------------------------------------- | -------------------------------- |
| `i` / `a`  | Enter Insert mode (before / after the cursor) | -                                |
| `o` / `O`  | Insert a new line (below / above)             | `Ctrl + Enter`                   |
| `Esc`      | Return to Normal mode                         | `Esc`                            |
| `v` / `V`  | Visual mode (selection) / Line visual mode    | `Shift + Arrows`                 |
| `y` / `yy` | Yank (Copy the selection / the entire line)   | `Ctrl + C`                       |
| `d` / `dd` | Delete (Cut the selection / the entire line)  | `Ctrl + X`                       |
| `"_d`      | Delete without copying (Black hole register)  | -                                |
| `p` / `P`  | Paste (After / before the cursor)             | `Ctrl + V`                       |
| `x`        | Delete the character under the cursor         | `Del`                            |
| `u`        | Undo                                          | `Ctrl + Z`                       |
| `Ctrl + r` | Redo                                          | `Ctrl + Y` or `Ctrl + Shift + Z` |
| `.`        | Repeat the last action                        | -                                |

---

## 2. Smart Selection (Text Objects)

| Shortcut | Action | VSCode Equivalent |
| ------------------ | -------------------------------------------------------------- | ------------------------------------------- |
| `v i w` | Select inside the word (inner word) | Double click / `Shift + Alt + Right` |
| `v a p` | Select the whole paragraph including surrounding empty lines | - |
| `v i (` or `v i )` | Select inside parentheses | `Shift + Alt + Right` inside parentheses |
| `v i "` or `v i '` | Select inside quotes | - |
| `v i {` or `v i }` | Select inside curly braces | - |
| `v i t` | Select inside an HTML tag | - |
| `c i "` | Delete inside quotes and enter Insert mode | (Very useful) |
| `d a (` | Delete the parentheses and their content | - |
| `y i {` | Copy the content inside curly braces | - |
| `y i [` | Copy the content inside square brackets | - |

*Kickstart Bonus (`mini.ai`): My config enhances this! For example, `v i q` selects inside the next pair of quotes (Quote).*

> [!TIP]
> These combinations work with all actions:
> `d` (delete), `c` (change), `y` (yank), `v` (visual) + `i`/`a` + object.

---

## 3. Global File Actions (Command-line)

By pressing `:`, you enter Command-line mode at the bottom of the screen for actions on the entire file.

| Command | Action | VSCode Equivalent |
| ---------------------- | --------------------------------------------- | -------------------------- |
| `:%d` | Delete all content in the file | `Ctrl + A` then `Del` |
| `:%y` | Yank (Copy) all content in the file | `Ctrl + A` then `Ctrl + C` |
| `:w` | Write (Save) | `Ctrl + S` |
| `:q` | Quit the current file | `Ctrl + W` |
| `:wq` | Save and quit | - |
| `:q!` | Force quit without saving | - |
| `:%s/old/new/g` | Replace "old" with "new" everywhere | `Ctrl + H` |
| `:%s/old/new/gc` | Replace with confirmation for each occurrence | - |
| `:e <file>` | Open a file | `Ctrl + O` |
| `:bn` / `:bp` | Next / Previous buffer | `Ctrl + Tab` |

---

## 4. Search & Navigation (Telescope)

| Shortcut      | Action                                                | VSCode Equivalent       |
| ------------- | ----------------------------------------------------- | ----------------------- |
| `Space s f`   | Search Files: Find a file by name                     | `Ctrl + P`              |
| `Space s g`   | Search by Grep: Search text across the entire project | `Ctrl + Shift + F`      |
| `Space s .`   | Search among recent files                             | `Ctrl + P` then recents |
| `Space Space` | Search among currently open files (buffers)           |                         |
| `Space /`     | Search text within the current file                   | `Ctrl + F`              |
| `Space s w`   | Search Word: Search for the word under the cursor     |                         |
| `Space s r`   | Search Resume: Reopen the last Telescope search       |                         |
| `Space s n`   | Search Neovim: Search inside your Neovim config files |                         |

---

## 5. Code & Features (LSP)

These shortcuts dynamically activate depending on the language you are coding in.

| Shortcut | Action | VSCode Equivalent |
| ---------- | ---------------------------------------------------------------- | ----------------- |
| `g r d` | Goto Definition | `F12` |
| `g r r` | Goto References: See where it's used | `Shift + F12` |
| `g r i` | Goto Implementation | `Ctrl + F12` |
| `g r n` | Rename variable/function across the project | `F2` |
| `g r a` | Goto Action: Display code actions (quick fixes) | `Ctrl + .` |
| `Space f` | Format the current file | `Shift + Alt + F` |
| `Space q` | Display the list of errors/diagnostics | |
| `K` | Show documentation for the item under the cursor | Mouse hover |

---

## 6. Autocompletion (IntelliSense)

My setup uses the `blink.cmp` plugin for autocompletion. The shortcuts are active **in Insert mode**.

| Shortcut | Action | VSCode Equivalent |
| -------------------------- | ----------------------------------------------------------- | --------------------- |
| `Ctrl + Space` | Force trigger autocompletion (e.g., after a dot) | `Ctrl + Space` |
| `Ctrl + y` or `Enter` | Confirm the selected suggestion (Yes) | `Enter` or `Tab` |
| `Ctrl + n` / `Down Arrow` | Move down in suggestions (Next) | `Down Arrow` |
| `Ctrl + p` / `Up Arrow` | Move up in suggestions (Previous) | `Up Arrow` |
| `Ctrl + k` | Show function signature help | `Ctrl + Shift + Space` |

---

## 7. Interface & Windows

| Shortcut | Action |
| ---------------- | ---------------------------------------------------------------- |
| `Ctrl + h/j/k/l` | Navigate between panes (left, down, up, right) |
| `Esc` | (In normal mode): Clear the search highlight from `/` |

---

## 8. General Tips

* If you forget what a shortcut starting with Space does, **press Space and wait a second**: a menu will appear at the bottom of the screen to remind you of possible continuations (which-key).
* To exit the integrated terminal in Neovim and return to normal mode, press `Esc` twice.
* `Ctrl + o` in Insert mode executes **a single command** in Normal mode and then immediately returns to Insert mode. Great for quick movements without leaving insert mode.

---

## 9. Git inside Neovim (lazygit.nvim)

### Shortcuts

| Shortcut | Action |
| ------------ | ----------------------------------------------------------- |
| `Space l g` | Open LazyGit (floating window on the current repository) |
| `Space l f` | Filter the whole project's commits (history) |
| `Space l c` | Filter the current file's commits only |

### Commands

| Command | Action |
| --------------------------- | ---------------------------------------------------------- |
| `:LazyGit` | Open lazygit (current directory) |
| `:LazyGitCurrentFile` | Open lazygit at the root of the current file's Git project |
| `:LazyGitConfig` | Open lazygit configuration file |
| `:LazyGitFilter` | Browse the project's commit history |
| `:LazyGitFilterCurrentFile` | Browse the current file's commit history |

> See `tools/git/lazygit.md` for the full LazyGit cheatsheet.
