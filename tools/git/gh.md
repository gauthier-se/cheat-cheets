# GitHub CLI (gh) Cheat-Sheet

## Authentication & Configuration

| Command | Description |
| --- | --- |
| `gh auth login` | Authenticate with a GitHub host |
| `gh auth logout` | Log out of a GitHub host |
| `gh auth status` | View authentication status |
| `gh auth refresh -s <scope>` | Refresh credentials with new scopes |
| `gh auth token` | Print the current authentication token |
| `gh auth setup-git` | Configure git to use gh as a credential helper |
| `gh config get <key>` | Get a configuration value |
| `gh config set <key> <value>` | Set a configuration value (e.g. `editor`) |
| `gh config list` | List all configuration values |

## Repositories

| Command | Description |
| --- | --- |
| `gh repo create <name>` | Create a new repository |
| `gh repo create --private --source=. --push` | Create a repo from the current directory and push |
| `gh repo clone <owner>/<repo>` | Clone a repository |
| `gh repo fork <owner>/<repo>` | Fork a repository |
| `gh repo view` | View the current repository in the terminal |
| `gh repo view --web` | Open the repository in the browser |
| `gh repo list <owner>` | List repositories owned by a user or org |
| `gh repo rename <new-name>` | Rename the current repository |
| `gh repo delete <owner>/<repo>` | Delete a repository |
| `gh repo sync` | Sync a forked repository with its upstream |
| `gh repo set-default` | Set the default repo for the current directory |

## Pull Requests

| Command | Description |
| --- | --- |
| `gh pr create` | Create a pull request (interactive) |
| `gh pr create --fill` | Create a PR using commit info for title/body |
| `gh pr create -t <title> -b <body>` | Create a PR with a title and body |
| `gh pr create --draft` | Create a draft pull request |
| `gh pr list` | List pull requests |
| `gh pr status` | Show status of relevant pull requests |
| `gh pr view <number>` | View a pull request |
| `gh pr view --web` | Open the pull request in the browser |
| `gh pr checkout <number>` | Check out a pull request locally |
| `gh pr diff <number>` | View the changes of a pull request |
| `gh pr checks` | Show CI status for a pull request |
| `gh pr review --approve` | Approve a pull request |
| `gh pr review --request-changes -b <msg>` | Request changes on a pull request |
| `gh pr review --comment -b <msg>` | Comment on a pull request |
| `gh pr comment <number> -b <msg>` | Add a comment to a pull request |
| `gh pr merge <number>` | Merge a pull request |
| `gh pr merge --squash --delete-branch` | Squash-merge and delete the branch |
| `gh pr ready <number>` | Mark a draft pull request as ready for review |
| `gh pr close <number>` | Close a pull request |
| `gh pr reopen <number>` | Reopen a closed pull request |

## Issues

| Command | Description |
| --- | --- |
| `gh issue create` | Create an issue (interactive) |
| `gh issue create -t <title> -b <body>` | Create an issue with a title and body |
| `gh issue list` | List issues |
| `gh issue list --label <label>` | List issues filtered by label |
| `gh issue status` | Show status of relevant issues |
| `gh issue view <number>` | View an issue |
| `gh issue view --web` | Open the issue in the browser |
| `gh issue comment <number> -b <msg>` | Comment on an issue |
| `gh issue close <number>` | Close an issue |
| `gh issue reopen <number>` | Reopen a closed issue |
| `gh issue edit <number> --add-label <label>` | Edit an issue (labels, assignees, etc.) |

## GitHub Actions (Workflows & Runs)

| Command | Description |
| --- | --- |
| `gh workflow list` | List workflows |
| `gh workflow view <workflow>` | View a workflow |
| `gh workflow run <workflow>` | Manually trigger a workflow |
| `gh workflow enable <workflow>` | Enable a workflow |
| `gh workflow disable <workflow>` | Disable a workflow |
| `gh run list` | List recent workflow runs |
| `gh run view <run-id>` | View a workflow run |
| `gh run view <run-id> --log` | View the logs of a run |
| `gh run watch <run-id>` | Watch a run until it completes |
| `gh run rerun <run-id>` | Re-run a failed workflow run |
| `gh run cancel <run-id>` | Cancel a workflow run |

## Releases

| Command | Description |
| --- | --- |
| `gh release create <tag>` | Create a release |
| `gh release create <tag> <files>` | Create a release and upload assets |
| `gh release list` | List releases |
| `gh release view <tag>` | View a release |
| `gh release download <tag>` | Download release assets |
| `gh release upload <tag> <files>` | Upload assets to a release |
| `gh release delete <tag>` | Delete a release |

## Gists

| Command | Description |
| --- | --- |
| `gh gist create <file>` | Create a gist from a file |
| `gh gist create -` | Create a gist from stdin |
| `gh gist create --public <file>` | Create a public gist |
| `gh gist list` | List your gists |
| `gh gist view <id>` | View a gist |
| `gh gist edit <id>` | Edit a gist |
| `gh gist clone <id>` | Clone a gist |

## API & Extensions

| Command | Description |
| --- | --- |
| `gh api <endpoint>` | Make an authenticated GitHub API request |
| `gh api repos/<owner>/<repo>/issues` | Example: list issues via the API |
| `gh api --paginate <endpoint>` | Paginate through all results |
| `gh api -f key=value <endpoint>` | Send a POST request with fields |
| `gh extension list` | List installed extensions |
| `gh extension install <owner>/<repo>` | Install an extension |
| `gh extension upgrade --all` | Upgrade all installed extensions |
| `gh extension remove <name>` | Remove an extension |
| `gh browse` | Open the current repository in the browser |
| `gh search repos <query>` | Search for repositories |
| `gh search issues <query>` | Search for issues |
