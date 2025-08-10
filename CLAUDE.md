# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is `go-starter`, a minimal Go template repository for creating new Go projects. The codebase is intentionally simple with just a basic "Hello World" main.go file.

## Essential Commands

### Testing
```bash
go test -v ./...
```

### Code Quality
```bash
go vet .
```

### Static Analysis
The project uses staticcheck for static analysis. Install and run locally:
```bash
go install honnef.co/go/tools/cmd/staticcheck@2023.1.2
staticcheck ./...
```

### Vulnerability Scanning
Uses govulncheck for vulnerability scanning:
```bash
go install golang.org/x/vuln/cmd/govulncheck@latest
govulncheck ./...
```

### Building
```bash
go build -o main .
```

### Running
```bash
go run .
```

## Architecture

This is a minimal Go starter template with:
- `main.go`: Simple "Hello World" application entry point
- `go.mod`: Module definition targeting Go 1.19
- `.github/workflows/ci-pipeline.yml`: CI pipeline with build, test, vet, staticcheck, and vulnerability scanning

## CI/CD Pipeline

The GitHub Actions workflow runs on push/PR to main and includes:
1. **build** job: `go vet` and `go test -v ./...`
2. **static-checks** job: staticcheck and govulncheck vulnerability scanning

Go version is configured as 1.19 in both go.mod and CI pipeline.