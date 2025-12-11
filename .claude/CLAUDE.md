# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository contains Claude Code artifacts (slash commands) for Senzing projects. Commands defined here are referenced by other Senzing repositories via versioned URLs.

## Repository Structure

- `commands/` - Versioned slash commands referenced via <https://raw.githubusercontent.com/senzing-factory/claude/refs/tags/v1/commands/>
  - `senzing.md` - Dispatcher with subcommands: `changelog-update`, `code-review`
  - `senzing-code-review.md` - PR/diff code review checklist
  - `senzing-changelog-update.md` - Semantic versioning and CHANGELOG.md updates
- `.claude/commands/` - Project-local commands
  - `senzing.md` - Fetches instructions from the versioned commands
  - `senzing-issue-fix-proposal.md` - Issue fix code review

## CI/CD Workflows

All workflows use shared definitions from `senzing-factory/build-resources@v3`:

- **lint-repo.yaml** - Runs linters on push/PR
- **spellcheck.yaml** - Runs cspell on PRs
- **claude-pr-review.yaml** - Automated Claude PR review on PRs

## Standards

- **Changelog**: Follow [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)
- **Versioning**: Follow [Semantic Versioning](https://semver.org/spec/v2.0.0.html)
- **Markdown**: Follow [CommonMark](https://commonmark.org/) specification, format with prettier
- **Code Style**: See <https://raw.githubusercontent.com/senzing-garage/knowledge-base/refs/heads/main/WHATIS/code-style.md>

## Spell Checking

Custom words are defined in [.vscode/cspell.json](.vscode/cspell.json). Add project-specific terms there to avoid spell check failures.
