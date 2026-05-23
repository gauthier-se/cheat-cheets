# zoxide (zi) — Smarter cd

Replaces `cd`. Remembers which directories you use most frequently, so you can "jump" to them in just a few keystrokes.

```bash
# Jump to a directory that matches the query
z projects

# Interactive search with fzf
zi

# Add a directory manually
zoxide add ~/Projects/my-project

# List known directories with their scores
zoxide query -ls
```

> [!TIP]
> **Personal Configuration**
> Add this to your `.zshrc`:
> ```bash
> eval "$(zoxide init zsh)"
> ```

```bash
brew install zoxide
```
