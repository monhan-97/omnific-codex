# Omnific Codex

Shared Codex Plugin marketplace for Omnific development workflows.

## Included Plugin

`omnific-development` provides reusable Skills for:

- Omnific coding standards
- Conventional Commit workflows
- React project conventions
- OpenAPI API changes
- Changesets package releases
- Graphify project workflows

## Install

Clone this repository on the target computer, then register the local marketplace and install the
Plugin:

```bash
git clone <repository-url> omnific-codex
cd omnific-codex
codex plugin marketplace add "$(pwd)"
codex plugin add omnific-development@omnific
```

Start a new Codex thread after installation so the Skills are discovered.

## Update

Pull the latest source and reinstall the Plugin:

```bash
git pull --ff-only
codex plugin add omnific-development@omnific
```
