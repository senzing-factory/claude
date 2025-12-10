# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a **command definition repository** for Claude Code, providing specialized prompts and workflows for Senzing software development. It contains Claude command definitions for automated code reviews, changelog management, and issue resolution across the Senzing ecosystem.

## Architecture

**Three-Layer Command System:**

1. **Command Dispatcher** (`commands/senzing.md`) - Entry point that routes to subcommands (`changelog-update` or `code-review`), referencing versioned remote commands from `senzing-factory/claude@v1`

2. **Specialized Commands** (`commands/`) - Standalone commands for PR analysis (`senzing-code-review.md`) and changelog generation (`senzing-changelog-update.md`)

3. **Extended Commands** (`.claude/commands/`) - Wrappers delegating to remote GitHub versions and external knowledge-base workflows

**External Dependencies:**
- `senzing-factory/build-resources` (v3): Reusable GitHub workflows
- `senzing-garage/knowledge-base`: Code style guides and Claude memory configs

## Quality Checks

Linting runs automatically on PRs to main via `.github/workflows/lint-repo.yaml`:
- YAML validation (`.github/linters/.yaml-lint.yml`)
- Code duplication detection (threshold: 5 lines)
- GitHub Actions security scanning via zizmor
- Spell checking via cspell
- Prettier formatting for JSON, Markdown, YAML

## Code Style

- Follow external Senzing code style guide: `https://raw.githubusercontent.com/senzing-garage/knowledge-base/refs/heads/main/WHATIS/code-style.md`
- Markdown must comply with CommonMark specification
- CHANGELOG.md follows Keep a Changelog format with Semantic Versioning

## Claude Settings

- `includeCoAuthoredBy: false` - Co-author attribution disabled in commits
- GitHub Actions use `CLAUDE_CODE_OAUTH_TOKEN` secret for Claude-powered PR reviews
