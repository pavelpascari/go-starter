# go-starter

`go-starter` is a public golang starter repo template. 
It is useful for getting started with a new project. 


## How to use

```bash
gh repo create <name> \
  --public \
  --template https://github.com/pavelpascari/go-starter
```

## Features

### Go Development Essentials
- [x] **Go 1.24.6 module structure** - Modern Go module with latest stable version
- [x] **Hello World application** - Simple main.go entry point for immediate testing
- [x] **Essential Go commands** - Configured for build, test, run, and quality checks

### Code Quality & Security
- [x] **GitHub Actions CI/CD Pipeline** - Complete workflow on push/PR to main
  - [x] **Automated testing** - `go test -v ./...`
  - [x] **Code vetting** - `go vet` for static analysis
  - [x] **Staticcheck integration** - Advanced static analysis using [@dominikh](https://github.com/dominikh)'s `dominikh/staticcheck-action`
  - [x] **Vulnerability scanning** - `govulncheck` with SARIF reports using [@Templum](https://github.com/Templum)'s `Templum/govulncheck-action`
- [x] **Dependabot security scanning** - Automated dependency updates for `go` and `github-actions`
- [x] **Claude Code integration** - CLAUDE.md with project-specific guidance and commands

### Development Workflow
- [x] **Build automation** - `go build -o main .`
- [x] **Test automation** - Comprehensive test runner configuration
- [x] **Quality gates** - All CI checks must pass before merge

## Post-Template Setup

After using this template, follow these steps to customize for your project:

### 1. Update Project Identity
```bash
# Replace go-starter with your project name
find . -name "*.md" -exec sed -i '' 's/go-starter/YOUR_PROJECT_NAME/g' {} \;
find . -name "*.go" -exec sed -i '' 's/go-starter/YOUR_PROJECT_NAME/g' {} \;

# Update go.mod module name
go mod edit -module github.com/YOUR_USERNAME/YOUR_PROJECT_NAME
```

### 2. Customize Application
- Replace the "Hello World" code in `main.go` with your application logic
- Update `CLAUDE.md` with your project-specific instructions
- Modify this README.md to describe your actual project

### 3. Remove Template References
```bash
# Remove template-specific content
git rm -r .github/ISSUE_TEMPLATE/ 2>/dev/null || true
git rm -r .github/PULL_REQUEST_TEMPLATE/ 2>/dev/null || true

# Update README to remove template references
# (Replace this entire "Post-Template Setup" section with your project documentation)
```

### 4. Verify Setup
```bash
go mod tidy
go test -v ./...
go vet .
staticcheck ./...
govulncheck ./...
```

