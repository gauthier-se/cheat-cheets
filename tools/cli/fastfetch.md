# fastfetch — System Info

Aesthetic system info (OS, CPU, RAM...). `neofetch` replacement.

```bash
fastfetch
```

## Options

| Command | Description |
| :--- | :--- |
| `fastfetch -c <file.json>` | Use specific config |
| `fastfetch --logo <name>` | Force logo (`apple`, `ubuntu`) |
| `fastfetch --list-logos` | List built-in logos |
| `fastfetch --list-presets` | List config presets |
| `fastfetch -c hardware` | Load "hardware" preset |
| `fastfetch --gen-config` | Generate config in `~/.config/fastfetch/` |

## Examples

* **Startup info**: Add `fastfetch` to `~/.zshrc`.
* **Custom modules**: Run `fastfetch --gen-config` and edit the JSON file to remove unwanted lines.

## Installation

```bash
brew install fastfetch
```
