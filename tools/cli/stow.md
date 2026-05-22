# stow — Dotfiles Manager

Manages symlinks to organize configuration files (dotfiles).

```bash
# Typical structure:
# ~/dotfiles/
#   nvim/.config/nvim/init.lua
#   zsh/.zshrc
#   tmux/.tmux.conf

# Install symlinks for nvim
cd ~/dotfiles && stow nvim

# Remove symlinks
stow -D nvim

# Reinstall (remove + install)
stow -R nvim

# Simulate without applying (dry run)
stow -n -v nvim
```

```bash
brew install stow
```
