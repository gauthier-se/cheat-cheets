# Nix Flakes

Reproducible Nix projects: `flake.nix` declares inputs/outputs, `flake.lock` pins exact versions (like a lockfile).

```bash
nix flake init -t ~/dotfiles/nix#python
```

## Anatomy

```nix
{
  description = "…";
  inputs = {
    nixpkgs.url = "github:NixOS/nixpkgs/nixpkgs-unstable";
  };
  outputs = { self, nixpkgs }: {
    devShells.<system>.default = …;   # what the flake provides
    packages.<system>.default = …;
    templates.<name> = …;
  };
}
```

## Commands

| Command | Description |
| :--- | :--- |
| `nix flake init -t <flake>#<template>` | Scaffold from a template |
| `nix flake show <flake>` | List what a flake exposes |
| `nix flake check` | Validate all outputs |
| `nix flake update` | Bump every input in `flake.lock` |
| `nix flake update <input>` | Bump a single input |
| `nix develop` | Enter the flake's devshell manually |
| `nix build .#<output>` | Build an output (result in `./result`) |

## Examples

```bash
# 1. New project environment from my templates (python, node, go, java)
nix flake init -t ~/dotfiles/nix#go

# 2. Update project toolchain, then reload the env
nix flake update && direnv reload

# 3. Inspect a remote flake
nix flake show github:gauthier-se/dotfiles?dir=nix
```

> [!WARNING]
> In a git repo, a flake only sees **tracked files**.
> `git add flake.nix .envrc` first, or you'll get `path '/nix/store/…' does not exist`.
> Commit `flake.nix`, `flake.lock` and `.envrc`; gitignore `.direnv/`.
