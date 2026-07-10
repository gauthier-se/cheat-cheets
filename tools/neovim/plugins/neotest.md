# Neotest (Test runner — Go)

Run and debug tests from inside the editor. Uses the `neotest-golang` adapter, and reuses `nvim-dap-go` (already configured in my DAP setup) for debugging.

## My keymaps (`<leader>t` = Test)

| Shortcut | Action |
| :--- | :--- |
| `<leader>tt` | Run the **nearest** test (under the cursor) |
| `<leader>tf` | Run all tests in the current **file** |
| `<leader>td` | **Debug** the nearest test (stops on breakpoints via DAP) |
| `<leader>ts` | Toggle the test **summary** panel (tree of tests) |
| `<leader>to` | Open the **output** of the nearest test |
| `<leader>tO` | Toggle the output **panel** |

## Inside the summary panel (`<leader>ts`)

| Key | Action |
| :--- | :--- |
| `r` | Run the test under the cursor |
| `d` | Debug the test under the cursor |
| `o` | Show the test output |
| `<Enter>` | Expand / jump to the test |
| `m` | Mark a test (then `R` runs all marked) |

## Status markers

| Symbol | Meaning |
| :--- | :--- |
| ✅ | Passed |
| ❌ | Failed |
| 🏃 | Running |
| (empty) | Not run yet |

> Requires `delve` for debugging — it installs automatically via Mason on first debug (`<leader>td`).
