# Basic Shortcuts (Vim / Neovim)

## 1. Basic Motions (Normal Mode)

| Shortcut | Action |
| :--- | :--- |
| `h` | Left |
| `j` | Down |
| `k` | Up |
| `l` | Right |
| `w` | Jump forward to the start of a word |
| `W` | Jump forward to the start of a word (words can contain punctuation) |
| `b` | Jump backward to the start of a word |
| `B` | Jump backward to the start of a word (words can contain punctuation) |
| `e` | Jump forward to the end of a word |
| `0` | Jump to the start of the line |
| `^` | Jump to the first non-blank character of the line |
| `$` | Jump to the end of the line |
| `gg` | Go to the first line of the document |
| `G` | Go to the last line of the document |
| `{` | Jump to the previous paragraph |
| `}` | Jump to the next paragraph |
| `%` | Jump to the matching parenthesis/bracket/brace |
| `Ctrl + d` | Scroll down half a page |
| `Ctrl + u` | Scroll up half a page |
| `Ctrl + f` | Scroll forward one full page |
| `Ctrl + b` | Scroll backward one full page |
| `H` | Jump to the Top of the visible screen |
| `M` | Jump to the Middle of the visible screen |
| `L` | Jump to the Bottom of the visible screen |
| `:<n>` | Go to line number `n` (e.g., `:42`) |

## 2. Main Modes

| Shortcut | Action |
| :--- | :--- |
| `i` | Enter **Insert** mode (before cursor) |
| `I` | Enter **Insert** mode (at the beginning of the line) |
| `a` | Enter **Insert** mode (after cursor) |
| `A` | Enter **Insert** mode (at the end of the line) |
| `o` | Insert a new line below and enter **Insert** mode |
| `O` | Insert a new line above and enter **Insert** mode |
| `v` | Enter **Visual** mode (character selection) |
| `V` | Enter **Visual Line** mode (whole line selection) |
| `Ctrl + v` | Enter **Visual Block** mode (rectangular selection) |
| `Esc` | Return to **Normal** mode |
| `:` | Enter **Command-line** mode (e.g., `:w` to save, `:q` to quit) |
| `R` | Enter **Replace** mode (overwrites existing characters) |

## 3. Text Editing (Normal Mode)

| Shortcut | Action |
| :--- | :--- |
| `x` | Delete the character under the cursor |
| `X` | Delete the character before the cursor |
| `dw` | Delete up to the next word |
| `dd` | Delete the entire line |
| `D` | Delete from the cursor to the end of the line |
| `cw` | Change the word (deletes it and enters Insert mode) |
| `cc` | Change the entire line |
| `C` | Change from the cursor to the end of the line |
| `s` | Delete the character and enter Insert mode |
| `S` | Delete the line and enter Insert mode |
| `yy` | Yank (Copy) the entire line |
| `yw` | Yank (Copy) the word |
| `p` | Put (Paste) after the cursor |
| `P` | Put (Paste) before the cursor |
| `u` | Undo the last action |
| `Ctrl + r` | Redo the undone action |
| `.` | Repeat the last editing action |
| `J` | Join the next line to the current line |
| `~` | Toggle case of the character under the cursor |
| `>>` | Indent the line |
| `<<` | Un-indent the line |

## 4. Search

| Shortcut | Action |
| :--- | :--- |
| `/text` | Search for "text" forward |
| `?text` | Search for "text" backward |
| `n` | Go to the next occurrence |
| `N` | Go to the previous occurrence |
| `*` | Search for the word under the cursor forward |
| `#` | Search for the word under the cursor backward |
| `:noh` | Clear search highlighting |

## 5. Registers and Macros

| Shortcut | Action |
| :--- | :--- |
| `"ay` | Yank (Copy) into register `a` |
| `"ap` | Put (Paste) from register `a` |
| `qa` | Start recording macro in register `a` |
| `q` | Stop recording macro |
| `@a` | Play macro `a` |
| `@@` | Replay the last macro |
| `10@a` | Play macro `a` 10 times |

## 6. Marks (Bookmarks)

| Shortcut | Action |
| :--- | :--- |
| `ma` | Set mark `a` at the current cursor position |
| `` `a `` | Jump back to mark `a` (exact exact row and column) |
| `'a` | Jump back to mark `a` (first non-blank character of the line) |
| `:marks` | List all active marks |
