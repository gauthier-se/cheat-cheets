# nix-darwin — Declarative macOS

The whole system (CLI packages, GUI casks, macOS settings, fonts, services, dotfiles) is defined in `~/dotfiles/nix/` and applied with one command.

```bash
sudo darwin-rebuild switch --flake ~/dotfiles/nix    # alias: update
```

## Layout

| File | Role |
| :--- | :--- |
| `nix/flake.nix` | Entry point — inputs, hostname, user |
| `nix/darwin/configuration.nix` | System layer: `system.defaults`, homebrew casks, fonts, launchd services |
| `nix/home/home.nix` | User layer: CLI packages, direnv, dotfiles symlinks |
| `configs/**` | Actual dotfiles, symlinked out-of-store → editable without rebuild |

## Commands

| Command | Description |
| :--- | :--- |
| `update` | Apply the config (alias for `sudo darwin-rebuild switch --flake ~/dotfiles/nix`) |
| `darwin-rebuild --list-generations` | List system generations |
| `sudo darwin-rebuild --rollback` | Instant rollback to the previous generation |
| `nix flake update --flake ~/dotfiles/nix` | Bump nixpkgs & friends, then `update` |
| `brew list` | Casks/brews still managed by Homebrew (declared in the flake, `cleanup = "zap"`) |

## Where does X go?

| Need | Where |
| :--- | :--- |
| CLI tool, daily use | `home.packages` in `home/home.nix` |
| GUI app | `homebrew.casks` in `darwin/configuration.nix` |
| Mac App Store app | `homebrew.masApps` (needs App Store sign-in) |
| Project toolchain | the project's own `flake.nix` (devshell) |
| macOS setting | `system.defaults` (or `CustomUserPreferences` for third-party domains) |
| New dotfile | `configs/<tool>/` + a `link` entry in `home.nix` |

## Examples

```bash
# 1. Add a CLI tool permanently
#    home.nix: home.packages = [ … pkgs.htop ];
update

# 2. Something broke after a rebuild
sudo darwin-rebuild --rollback

# 3. Upgrade everything (packages pinned by flake.lock)
nix flake update --flake ~/dotfiles/nix && update

# 4. Fresh machine bootstrap (see nix/README.md)
xcode-select --install
git clone https://github.com/gauthier-se/dotfiles.git ~/dotfiles
curl -fsSL https://install.determinate.systems/nix | sh -s -- install --determinate
sudo nix run nix-darwin/master#darwin-rebuild -- switch --flake ~/dotfiles/nix
```

> [!NOTE]
> Config edits under `configs/` (nvim, tmux, zsh, alacritty…) apply instantly — the files are
> symlinked out of the store. A rebuild is only needed when packages, casks, services or
> `system.defaults` change.
