# pnpm — Fast, Disk Space Efficient Package Manager

Most commands are identical to npm, but with performance benefits.

| Command | Description |
| :--- | :--- |
| `pnpm init` | Initialize a new `package.json` |
| `pnpm install` / `pnpm i` | Install all dependencies |
| `pnpm add <pkg>` | Install a package as a dependency |
| `pnpm add -D <pkg>` | Install a package as a devDependency |
| `pnpm add -g <pkg>` | Install a package globally |
| `pnpm remove <pkg>` | Uninstall a package |
| `pnpm update` | Update dependencies |
| `pnpm run <script>` | Run a custom script defined in `package.json` |
| `pnpm exec <cmd>` | Execute a shell command in scope of a project (similar to `npx`) |

## pnpm Specifics

| Command | Description |
| :--- | :--- |
| `pnpm dlx <cmd>` | Fetch a package from the registry and execute it (equivalent to `npx`) |
| `pnpm store prune` | Removes unreferenced packages from the global store (frees up disk space) |
| `pnpm audit --fix` | Check for and automatically fix known security issues |

## Monorepo / Workspaces (`pnpm-workspace.yaml`)

pnpm shines when working with monorepos.

| Command | Description |
| :--- | :--- |
| `pnpm --filter <pkg> run build`| Run the `build` script only in the specific workspace package |
| `pnpm -r run build` | Run the `build` script recursively in all workspace packages |
| `pnpm add <pkg> --filter <workspace>` | Add a dependency only to a specific workspace package |
