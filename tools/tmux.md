# Tmux Cheatsheet

## 1. Core Concepts

Tmux is organized into 3 levels:

1. **Sessions** — The highest level, groups a global view of your work (e.g., "Alpha Project").
2. **Windows** — Like tabs in a browser, inside a Session.
3. **Panes** — Visible subdivisions of your terminal within the same Window.

> [!IMPORTANT] The Prefix
> By default, the prefix is `Ctrl + b`. All tmux commands start with this prefix.
> If you have remapped it (e.g., `Ctrl + space`), adjust accordingly.

---

## 2. Terminal Commands (Outside Tmux)

These commands are typed directly into your standard bash/zsh terminal.

| Command | Action |
| :--- | :--- |
| `tmux` | Start a new tmux session (without a specific name) |
| `tmux new -s session_name` | Start a new session named "session_name" |
| `tmux ls` | **List** all active background tmux sessions |
| `tmux a` | **Attach** to the most recently opened session |
| `tmux a -t session_name` | Attach to the session named "session_name" |
| `tmux kill-session -t name` | Kill a specific session running in the background |
| `tmux kill-server` | Kill all tmux sessions entirely |
| `tmux source ~/.tmux.conf` | Reload the tmux configuration |

---

## 3. Session Shortcuts (Inside Tmux)

| Shortcut | Action |
| :--- | :--- |
| `Prefix` then `d` | **Detach** the session (closes it visually but leaves it running in the background) |
| `Prefix` then `s` | Display the interactive visual list of **Sessions** (use `Enter` to switch) |
| `Prefix` then `$` | **Rename** the current session |
| `Prefix` then `(` | **Previous** session |
| `Prefix` then `)` | **Next** session |

---

## 4. Window Shortcuts (Tabs)

| Shortcut | Action |
| :--- | :--- |
| `Prefix` then `c` | **Create** a new Window |
| `Prefix` then `0` to `9` | Select a Window directly by its number |
| `Prefix` then `p` | Go to the **Previous** Window |
| `Prefix` then `n` | Go to the **Next** Window |
| `Prefix` then `w` | Display the interactive visual list of **Windows** |
| `Prefix` then `,` | **Rename** the current Window |
| `Prefix` then `&` | Close/Kill the current Window (Prompts for confirmation) |
| `Prefix` then `l` | Last active Window |

---

## 5. Pane Shortcuts (Splits)

| Shortcut | Action |
| :--- | :--- |
| `Prefix` then `%` | **Split Vertically** (left / right) |
| `Prefix` then `"` | **Split Horizontally** (top / bottom) |
| `Prefix` then `Arrow keys` | **Navigate** between Panes |
| `Prefix` then `o` | Move to the **next** Pane |
| `Prefix` then `;` | Return to the **last** active Pane |
| `Prefix` then `x` | **Close/Kill** the current Pane |
| `Prefix` then `z` | **Zoom / Unzoom** the current Pane (fullscreen toggle) |
| `Prefix` then `Space` | Toggle between predefined Pane layouts |
| `Prefix` then `{` | Move the Pane to the **left** |
| `Prefix` then `}` | Move the Pane to the **right** |
| `Prefix` then `!` | Convert the Pane into a new **Window** |
| `Prefix` then `q` | Show Pane numbers (then type the number to jump there) |

### Resizing Panes

| Shortcut | Action |
| :--- | :--- |
| Hold `Prefix` + `Arrow keys` | Hold `Ctrl + b` and use arrows to resize |
| `Prefix` then `Alt + 1` | Equal horizontal layout |
| `Prefix` then `Alt + 2` | Equal vertical layout |

---

## 6. Copy Mode (Scroll / Vi Mode)

Tmux keeps its own scrollback history. To navigate and copy text:

### Enter / Exit

| Shortcut | Action |
| :--- | :--- |
| `Prefix` then `[` | **Enter** Copy Mode |
| `q` or `Esc` | **Exit** Copy Mode |

### Navigate (in Copy Mode)

| Shortcut | Action |
| :--- | :--- |
| `h` / `j` / `k` / `l` | Move cursor (like Vim) |
| `Ctrl + u` / `Ctrl + d` | Move Half-page up / down |
| `g` | Go to the top of the history |
| `G` | Go to the bottom of the history |
| `/text` | Search text forwards (down) |
| `?text` | Search text backwards (up) |
| `n` / `N` | Next / Previous occurrence |

### Copy (in Copy Mode, vi-mode)

| Shortcut | Action |
| :--- | :--- |
| `Space` | Start text selection |
| `Enter` | Copy the selection and exit Copy Mode |
| `Prefix` then `]` | **Paste** the copied text |

---

## 7. Tmuxinator (Predefined Sessions)

Tmuxinator allows you to define session layouts in YAML format.

```bash
# Create a new project
tmuxinator new my-project

# Launch a project
tmuxinator start my-project

# List projects
tmuxinator list

# Edit an existing project
tmuxinator edit my-project

# Delete a project
tmuxinator delete my-project
```

Example of a `~/.config/tmuxinator/my-project.yml` file (Personal Setup):

```yaml
name: my-project
root: ~/Projects/my-project

windows:
  - editor:
      panes:
        - nvim
  - server:
      panes:
        - npm run dev
  - terminal:
      panes:
        - # empty shell
```
