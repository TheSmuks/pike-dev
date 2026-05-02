# Project Context

This file is auto-discovered by AI coding agents. It provides project-level context that guides agent behavior.

## Project Overview

- **Name**: pike-dev
- **Description**: Meta-repo hub for the Pike development toolchain ecosystem
- **Primary Language**: Shell (scripts), Markdown (documentation), Pike (submodule code)

## Build & Run

This is a meta-repo with no build step. Submodules are independent projects.

```bash
# Clone with all submodules
git clone --recurse-submodules https://github.com/TheSmuks/pike-dev.git

# Update all submodules
git submodule update --remote

# Update a specific submodule
git submodule update --remote repos/pvm
```

## Code Style

- Follow the conventions in each submodule's AGENTS.md
- Keep commit messages descriptive and conventional
- Update CHANGELOG.md under `[Unreleased]` for user-facing changes

## Project Structure

```
pike-dev/              # Hub repository
├── README.md          # This file
├── repos/             # Submodules directory
│   ├── pvm/           # Pike Version Manager
│   ├── pike-language-server/
│   ├── pmp/           # Package Manager
│   ├── pike-introspect/
│   ├── punit-tests/
│   ├── tree-sitter-pike/
│   ├── pike-ast/
│   ├── pmp-showcase/
│   ├── pike-ai-kb/
│   ├── pmp-example-module/
│   ├── pike-lsp/      # Maintenance mode
│   └── pike-cookbook/
├── .github/           # GitHub config
├── .omp/              # OMP harness config
└── docs/              # Documentation
```

## Testing

No tests in the hub repo. Each submodule has its own test suite.

## Error Handling

- Changes to submodules should be made in their respective repositories
- Hub repo only tracks submodule references (commit SHAs)
- Push submodule changes before updating the hub repo

## Agent Behavior

When an AI agent is working in this repository:

1. **Submodule awareness**: Changes to `repos/*` directories require separate commits in those repos
2. **Reference updates**: When a submodule is updated, commit the reference change in the hub repo
3. **No direct edits**: Do not edit files inside submodules from the hub repo — work in the submodule directly
4. **PR for hub changes**: Changes to hub repo files (README, docs, config) should still go through PRs

## Submodule Workflow

```bash
# 1. Work in the submodule
cd repos/pvm
# make changes, commit, push

# 2. Update hub repo to reference new commit
cd ..
git add repos/pvm
git commit -m "chore(pvm): update to latest version"
git push

# 3. Or use git submodule update --remote to update all
```

## References

- [Pike Programming Language](https://pike.lysator.liu.se/)
- [Pike on GitHub](https://github.com/pikelang/Pike)
- [docs/architecture.md](./docs/architecture.md) — Ecosystem architecture
