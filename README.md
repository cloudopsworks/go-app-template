# go-app-template

Go Lang Application Template with Github Action Gitops

## Tronador CLI Usage

### `project init` command

The `tronador project init --allow-network` command initializes your Go application with the following actions:

- Resolves the required `gh` and `go` tools; `tronador project version` resolves GitVersion separately
- Removes the existing go.mod file
- Initializes a new Go module with the current project name
- Runs `go mod tidy` to ensure dependencies are properly managed
- Replaces all instances of "hello-service" with your project name in all Go files

Usage:

Install Tronador CLI v0.5.0 or newer and GitHub CLI, authenticate `gh`
(`gh auth status` must succeed), and explicitly allow the repository-owner lookup:

```bash
tronador project init --allow-network
```

### `project version` command

The `tronador project version` command creates a VERSION file for your application using GitVersion:

- If the current commit is a Git tag, it extracts the version from the tag
- Otherwise, it uses GitVersion to generate a semantic version
- Replaces '+' with '-' in the version string for compatibility with Docker and Helm

Usage:

```bash
tronador project version
```
