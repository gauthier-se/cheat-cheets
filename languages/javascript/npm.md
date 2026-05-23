# npm — Node Package Manager

| Command | Description |
| :--- | :--- |
| `npm init -y` | Initialize a new `package.json` with default values |
| `npm install` | Install all dependencies listed in `package.json` |
| `npm install <pkg>` | Install a package and add it to `dependencies` |
| `npm install -D <pkg>` | Install a package and add it to `devDependencies` (e.g., testing tools, types) |
| `npm install -g <pkg>` | Install a package globally on your system |
| `npm uninstall <pkg>` | Remove a package from `node_modules` and `package.json` |
| `npm update` | Update dependencies to their latest versions according to `package.json` |
| `npm run <script>` | Run a custom script defined in `package.json` (e.g., `npm run dev`) |

## Useful Options

| Command | Description |
| :--- | :--- |
| `npm ci` | Clean install: deletes `node_modules` and installs exactly what's in `package-lock.json` (great for CI/CD) |
| `npm cache clean --force` | Clear the global npm cache (fixes weird installation issues) |
| `npm list -g --depth=0` | List globally installed packages without showing their dependencies |
| `npm outdated` | Check for outdated packages in your project |

## Examples

```bash
# 1. Start a new project
npm init -y

# 2. Install React and testing library
npm install react react-dom
npm install -D @testing-library/react

# 3. Clean install for production
npm ci --production
```
