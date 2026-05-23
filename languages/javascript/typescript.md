# TypeScript (tsc)

## CLI Commands

| Command | Description |
| :--- | :--- |
| `tsc --init` | Generate a `tsconfig.json` file with default compiler options |
| `tsc` | Compile all `.ts` files in the project according to `tsconfig.json` |
| `tsc --watch` / `tsc -w`| Run the compiler in watch mode (recompiles on file change) |
| `tsc <file.ts>` | Compile a specific file (ignores `tsconfig.json` unless specified) |
| `tsc --noEmit` | Only run type-checking without generating `.js` files (useful in pipelines) |

## Quick Execution Tools

Instead of compiling and running in two steps, you can use these tools to run TypeScript directly.

| Command | Description |
| :--- | :--- |
| `ts-node <file.ts>` | Execute a TypeScript file directly (requires `ts-node` package) |
| `tsx <file.ts>` | Modern, faster alternative to `ts-node` powered by esbuild |
| `npx tsx <file.ts>` | Run tsx without installing it globally |

## Recommended `tsconfig.json`


```json
{
  "compilerOptions": {
    /* Base Options */
    "esModuleInterop": true,
    "skipLibCheck": true,
    "target": "es2022",
    "allowJs": true,
    "resolveJsonModule": true,
    "moduleDetection": "force",
    "isolatedModules": true,
    "verbatimModuleSyntax": true,

    /* Strictness */
    "strict": true,
    "noUncheckedIndexedAccess": true,
    "noImplicitOverride": true,

    /* If transpiling with TypeScript (e.g., Node) */
    "module": "NodeNext",
    "outDir": "dist"
    
    /* If NOT transpiling with TypeScript (using a bundler like Vite/esbuild) */
    // "module": "preserve",
    // "noEmit": true,

    /* If your code runs in the DOM (uncomment) */
    // "lib": ["es2022", "dom", "dom.iterable"]
  }
}
```
