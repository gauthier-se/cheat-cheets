# Nix Devshells + direnv

Per-project environments that activate automatically on `cd` — replaces conda, nvm and sdkman.

```bash
nix flake init -t ~/dotfiles/nix#node && direnv allow
```

## Workflow

| Command | Description |
| :--- | :--- |
| `nix flake init -t ~/dotfiles/nix#<tpl>` | Create the env (`python`, `node`, `go`, `java`) |
| `direnv allow` | Trust `.envrc` (once per project, and after editing it) |
| `direnv reload` | Reload after changing `flake.nix` |
| `nix develop` | Enter the shell manually (without direnv) |
| `nix develop -c <cmd>` | Run one command inside the env |

## Per language

| Language | Ships with | Daily driver |
| :--- | :--- | :--- |
| Python | `python312`, `uv`, auto-created `.venv` | `uv add <pkg>`, `uv sync`, `uv run pytest` |
| Node | `nodejs_22`, `pnpm`, `typescript-language-server`, `prettierd`, `eslint_d` | `pnpm install`, `pnpm dev` |
| Go | `go`, `gopls`, `gotools`, `delve` | `go build`, `go test` |
| Java | `jdk21`, `maven` | `mvn …` |

## conda → nix/uv mapping

| conda | nix + uv |
| :--- | :--- |
| `conda create -n proj python=3.12` | `nix flake init -t ~/dotfiles/nix#python` |
| `conda activate proj` | automatic on `cd` (direnv) |
| `conda install numpy` | `uv add numpy` |
| `conda env export` | `pyproject.toml` + `uv.lock` (committed) |

## Examples

```bash
# 1. Change the Node version for ONE project
#    flake.nix: nodejs_22 -> nodejs_24, then:
direnv reload

# 2. Add a tool to the project env
#    flake.nix: packages = [ … postgresql ];
direnv reload

# 3. Python version bump: recreate the venv
rm -rf .venv && direnv reload
```

> [!NOTE]
> Neovim picks LSPs/formatters/debuggers from the shell's PATH (no Mason):
> launch `nvim` from inside the project and check with `:LspInfo`.
