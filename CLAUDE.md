# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a GitHub CLI extension written in Bash that helps manage chains of pull requests (PRs). A chain of PRs is where one PR is based upon another, which in turn is based on another, and so on.

## Key Commands for Development

### Testing the Script
```bash
# Run the script directly (from project root)
./gh-pr-chain [command]

# Install as gh extension for testing
gh extension install .

# Check version
./gh-pr-chain --version
```

### No Build/Lint Commands
This is a simple Bash script with no build process, package manager, or linting setup.

## Code Architecture

### Single-File Architecture
All functionality is contained in the `gh-pr-chain` bash script:
- **Command routing**: Case statement at the bottom (lines 241-295)
- **Core functions**:
  - `Next()` / `Last()`: Navigate forward in PR chains
  - `Previous()`: Navigate backward in PR chains
  - `MergePrevious()` / `MergeUpChain()`: Merge operations
  - `Create()` / `Insert()`: Create new PRs in chains
  - `SquashIntoPrevious()` / `SquashChain()`: Squash merge operations

### Key Implementation Details
- Uses `set -e` and `set -o pipefail` for fail-fast behavior
- Heavy reliance on `gh` CLI for GitHub API operations
- Uses `jq` for JSON parsing from `gh` responses
- Branch names are automatically generated from PR titles (sanitized and lowercased)
- Error handling through exit codes and conditional execution

### Dependencies
- `gh` (GitHub CLI) - for all GitHub operations
- `jq` - for JSON parsing
- Standard Unix tools: `git`, `bash`

### Notable Patterns
- PR chains are navigated by examining `baseRefName` (previous) and searching for PRs with current branch as base (next)
- The `@me` author filter is used to limit navigation to user's own PRs
- Empty commits are created when making draft PRs to satisfy GitHub's requirements
- Version is determined using `git describe --tags` from the script's directory