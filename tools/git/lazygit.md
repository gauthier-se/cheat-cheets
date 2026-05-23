# LazyGit Tutorial

LazyGit is a terminal user interface for Git. It transforms endless Git command lines (add, commit, push, rebase...) into a fast, keyboard-only interface.

## How to Launch LazyGit?

* **From the terminal:** Run `lazygit` inside any Git repository.
* **From Neovim (wt plugin):** Press `<leader>lg` to open it in a floating window (press `q` to close).

---

## The Interface (The 5 Main Panels)

LazyGit is divided into logical blocks (panels on the left, preview on the right).

Navigation between panels:
* Keys `1`, `2`, `3`, `4`, `5`
* Left/Right arrows (or `h` / `l`)
* Mouse click

> [!IMPORTANT]
> **Universal Shortcut**
> **`<Space>`** — used to select (Stage), unselect, or confirm an action in almost every panel.

> [!TIP]
> **Contextual Menu**
> Press `x` at any time to display all possible options available from your current location.

---

## 1. Status / Info Panel (Top Left)

Displays the current repository and branch. Mostly informative. Press `Enter` to view the latest git logs and errors.

---

## 2. Files Panel (Modified Files)

This is where you manage staging (`git add`) before committing.

| Key | Git Action | Description |
| :--- | :--- | :--- |
| `<Space>` | `git add` / `git reset` | **Stage/Unstage** the file under the cursor |
| `a` | `git add .` | Stage All files |
| `d` | `git checkout -- <file>` | **Discard** unsaved changes |
| `c` | `git commit -m` | Open the **Commit** window |
| `C` | `git commit -m` | Commit including *all* files at once |
| `e` | - | **Edit** the file in your editor |
| `o` | - | **Open** the file in the default system tool |
| `i` | `.gitignore` | Add the file to `.gitignore` |
| `S` | `git stash` | **Stash** all changes |

---

## 3. Local Branches Panel

Daily management of your git branches.

| Key | Git Action | Description |
| :--- | :--- | :--- |
| `<Space>` | `git checkout` | Checkout the selected branch |
| `n` | `git checkout -b` | Create a **New Branch** |
| `p` | `git pull` | **Pull** from the remote |
| `P` (Shift) | `git push` | **Push** to the remote |
| `f` | `git fetch` | Fetch without overwriting local work |
| `d` | `git branch -d` | Delete the local branch |
| `m` | `git merge` | **Merge** the selected branch into the current one |
| `r` | `git rebase` | **Rebase** the current branch onto the selected one |
| `R` | `git branch -m` | **Rename** the branch |
| `u` | - | Set the **upstream** branch |

---

## 4. Commits Panel (Local History)

Your commit history. Highly useful for modifying the past (Interactive Rebase).

| Key | Git Action | Description |
| :--- | :--- | :--- |
| `<Enter>` | `git show` | View modified files and lines of the commit |
| `c` | `git checkout <hash>` | **Checkout** an older commit |
| `t` | `git revert <hash>` | **Revert** — creates a commit that cleanly undoes it |
| `C` | `git cherry-pick` | **Cherry Pick** — copy the commit to your branch |
| `r` | Interactive Rebase | **Reword** — change the commit message |
| `e` | Interactive Rebase | **Edit** — modify the content of a commit |
| `s` | Interactive Rebase | **Squash** — merge with the previous commit |
| `f` | Interactive Rebase | **Fixup** — squash without keeping the message |
| `d` | Interactive Rebase | **Drop** — delete the commit |
| `g` | `git reset` | **Reset** — return to this commit |
| `A` | `git commit --amend` | **Amend** — add staged changes to the last commit |

---

## 5. Stash Panel

The Stash is a place to "set aside" modifications without committing them.

| Key | Git Action | Description |
| :--- | :--- | :--- |
| `s` | `git stash` | (From the *Files* panel) Save current work (prompts for a name) |
| `<Space>` | `git stash apply` | Apply changes from the stash |
| `g` | `git stash pop` | Apply AND delete the stash |
| `d` | `git stash drop` | Permanently delete the stash |
| `r` | `git stash apply` | Rename the stash |

---

## Global Shortcuts

These shortcuts work from any panel.

| Key | Action |
| :--- | :--- |
| `x` | Contextual menu (all available options) |
| `?` | Keyboard shortcuts menu |
| `/` | Filter / Search in the active panel |
| `[` / `]` | Navigate between tabs of a panel |
| `+` / `-` | Maximize / Minimize the right panel |
| `q` | Quit LazyGit |
| `@` | Open the log of executed git commands |
| `z` | Undo (undo the last git action via reflog) |
| `Z` | Redo |

---

## Conflict Resolution

When a merge or rebase creates conflicts:

| Key | Action |
| :--- | :--- |
| `<Space>` | Choose the block (ours / theirs) under the cursor |
| `b` | Keep **both** versions |
| `z` | Undo the conflict resolution |
| `<Enter>` | Open the file in the editor for manual resolution |
| `M` | Open an external merge tool |
