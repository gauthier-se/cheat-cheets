# Go cli

| Command            | Description                                               |
| :----------------- | :-------------------------------------------------------- |
| `go run <file.go>` | Compile and run a Go program on the fly                   |
| `go build`         | Compile the packages and dependencies into an executable  |
| `go test ./...`    | Run all tests in the current directory and subdirectories |
| `go fmt ./...`     | Automatically format all Go code to the standard style    |
| `go vet ./...`     | Examine code and report suspicious constructs (linting)   |

### Modules & Dependencies (`go mod`)

Go modules are the standard way to manage dependencies.

| Command | Description |
| :--- | :--- |
| `go mod init <module-name>` | Initialize a new Go module (creates `go.mod`) |
| `go mod tidy` | Add missing and remove unused modules (clean up `go.mod` & `go.sum`) |
| `go get <package>` | Download and install a specific package/dependency |
| `go get -u` | Update dependencies to their latest minor/patch versions |
| `go mod download` | Download modules to local cache (useful for CI/CD) |

### Workspaces (`go work`)

Useful for working with multiple modules simultaneously.

| Command | Description |
| :--- | :--- |
| `go work init <path>` | Initialize a workspace with the module at `<path>` |
| `go work use <path>` | Add a module to the current workspace |

### Environment

| Command | Description |
| :--- | :--- |
| `go env` | Print Go environment information (GOPATH, GOROOT, etc.) |
| `go version` | Print the installed Go version |

## Examples

```bash
# 1. Initialize a new project
mkdir myproject && cd myproject
go mod init github.com/username/myproject

# 2. Run your code
go run main.go

# 3. Build a standalone executable for Linux/AMD64 from Mac
GOOS=linux GOARCH=amd64 go build -o myapp main.go

# 4. Clean up dependencies before pushing to Git
go mod tidy
```
