# Delta — Git Diff Pager

Syntax-highlighting pager for `git diff`, `git log`, `git show`, `git blame`. Replaces the raw git diff with colored output, line numbers, and syntax highlighting. Repository: [dandavison/delta](https://github.com/dandavison/delta).

## Installation

Installed via Homebrew (macOS) or pacman (Arch) :

- macOS: `brew install git-delta`
- Arch: `sudo pacman -S git-delta`

Binary: `delta` (the package is called `git-delta` to avoid conflicts with another `delta` package).

## Configuration Integration

### `~/dotfiles/git/.gitconfig` (Personal Setup)

```ini
[core]
    pager = delta

[interactive]
    diffFilter = delta --color-only

[delta]
    features = catppuccin-mocha
    navigate = true
    line-numbers = true
    side-by-side = false

[merge]
    conflictstyle = zdiff3

[include]
    path = ~/dotfiles/git/catppuccin.gitconfig
```

- `core.pager = delta` → all git commands producing a diff use delta.
- `interactive.diffFilter` → used by `git add -p` (interactive patch).
- `features = catppuccin-mocha` → enables the `[delta "catppuccin-mocha"]` section from the included file.
- `navigate = true` → allows jumping between files/hunks with `n` and `N`.
- `line-numbers = true` → displays line numbers before/after.
- `side-by-side = false` → unified view (enable if using an ultrawide screen).
- `merge.conflictstyle = zdiff3` → better conflict markers (recommended by delta).

## Daily Usage

No workflow changes needed — delta hooks in automatically:

```bash
git diff                    # colored diff via delta
git diff HEAD~3             # same
git log -p                  # log with patches
git show <sha>              # commit
git stash show -p           # stash
git add -p                  # interactive patch (via diffFilter)
```

### Pager Navigation

With `navigate = true`:

| Key | Action |
| --- | --- |
| `n` | Next hunk |
| `N` | Previous hunk |
| `q` | Quit |
| `/` | Search (standard less behavior) |

### Temporary Bypass

To disable delta on a specific command:

```bash
git --no-pager diff
GIT_PAGER=cat git diff
```

## Useful Options

- `side-by-side = true` → side-by-side view (useful on large screens or via `git -c delta.side-by-side=true diff`).
- `delta --light` / `--dark` → force light/dark mode.
- `delta < file.diff` → use delta on a standalone `.diff` or `.patch` file.
- `git blame <file> | delta` → colored blame.

## Verify Configuration

```bash
delta --version
git config --list --show-origin | rg delta
delta --show-config         # displays active delta configuration
delta --list-languages      # supported languages for syntax highlighting
delta --list-syntax-themes  # syntax themes (from bat)
```