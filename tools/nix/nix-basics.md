# Nix — Basics

Declarative package manager: everything lives in an immutable `/nix/store`, nothing is ever modified in place.

```bash
nix run nixpkgs#cowsay -- "hello"
```

## Core concepts

| Concept | Description |
| :--- | :--- |
| Store | `/nix/store/<hash>-<name>/` — immutable, several versions coexist |
| Derivation | Build recipe (`.drv`) — inputs fully determine the output hash |
| Generation | System snapshot created by every rebuild — instant rollback |
| Garbage collection | Old generations stay on disk until collected |

## Everyday commands

| Command | Description |
| :--- | :--- |
| `nix search nixpkgs <term>` | Search a package (or https://search.nixos.org) |
| `nix shell nixpkgs#<pkg>` | Try a tool in the current shell only |
| `nix run nixpkgs#<pkg> -- <args>` | Run a tool without installing it |
| `nix-collect-garbage --delete-older-than 14d` | Free disk space |
| `nix store gc` | Garbage-collect unreferenced store paths |
| `readlink $(which <bin>)` | See where a binary comes from in the store |
| `nix repl` | Explore the Nix language interactively |

## Examples

```bash
# 1. Try htop without installing anything (gone when the shell exits)
nix shell nixpkgs#htop

# 2. One-shot run
nix run nixpkgs#nodejs_22 -- --version

# 3. Several tools at once
nix shell nixpkgs#jq nixpkgs#yq

# 4. Cleanup after experimenting
nix-collect-garbage --delete-older-than 14d
```

> [!NOTE]
> `nix shell` replaces the old `brew install → test → uninstall` reflex.
> If a tool deserves to stay, it deserves a line in the config (`home.nix` or a project flake).
