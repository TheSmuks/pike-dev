# pike-dev

Pike development toolchain hub — meta-repo with git submodules for all Pike utilities, tooling, and language support.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## About

This is a hub repository that aggregates all Pike-related projects under [TheSmuks](https://github.com/TheSmuks) as git submodules. It provides a single entry point for discovering, cloning, and working with the Pike development ecosystem.

## Included Projects

| Project | Description | Status |
|---------|-------------|--------|
| [pvm](https://github.com/TheSmuks/pvm) | Pike Version Manager — install, manage, and switch between multiple Pike versions | Active |
| [pike-language-server](https://github.com/TheSmuks/pike-language-server) | Tier-3 Language Server Protocol implementation for Pike | Active |
| [pmp](https://github.com/TheSmuks/pmp) | Package manager for Pike modules — install, version, and resolve dependencies | Active |
| [pike-introspect](https://github.com/TheSmuks/pike-introspect) | Pike runtime introspection module and agent skill for LLM-assisted development | Active |
| [punit-tests](https://github.com/TheSmuks/punit-tests) | JUnit-inspired testing framework for Pike | Active |
| [tree-sitter-pike](https://github.com/TheSmuks/tree-sitter-pike) | Pike grammar for tree-sitter — covers Pike 8.0.1116 | Active |
| [pike-ast](https://github.com/TheSmuks/pike-ast) | AST library for Pike source code — tokenization, parsing, querying, and pattern matching | Active |
| [pike-ai-kb](https://github.com/TheSmuks/pike-ai-kb) | Pike language knowledge base for AI code generation | Active |
| [pmp-example-module](https://github.com/TheSmuks/pmp-example-module) | Minimal example of a pmp-installable Pike module | Active |
| [pike-lsp](https://github.com/TheSmuks/pike-lsp) | LSP implementation for Pike with VS Code extension | ⚠️ Maintenance — superseded by [pike-language-server](https://github.com/TheSmuks/pike-language-server) |
| [pike-cookbook](https://github.com/TheSmuks/pike-cookbook) | Complete Pike 8.0 programming cookbook | Active |

## Quick Start

Clone with all submodules:

```bash
git clone --recurse-submodules https://github.com/TheSmuks/pike-dev.git
```

Or clone first, then initialize submodules:

```bash
git clone https://github.com/TheSmuks/pike-dev.git
cd pike-dev
git submodule update --init --recursive
```

Update all submodules to their latest commits:

```bash
git submodule update --remote
```

## Project Categories

### Language Tooling
- **pike-language-server** — LSP server (VSCode, etc.)
- **pike-lsp** — Previous LSP implementation (maintenance mode)
- **tree-sitter-pike** — Grammar for syntax highlighting and AST queries
- **pike-ast** — Pure-Pike AST library

### Package & Version Management
- **pmp** — Pike module package manager
- **pvm** — Pike version manager
- **pmp-example-module** — Minimal pmp module template

### Developer Experience
- **punit-tests** — Testing framework
- **pike-introspect** — Runtime introspection
- **pike-cookbook** — Recipes and examples

### AI & LLM Support
- **pike-ai-kb** — Knowledge base for AI code generation
- **pike-introspect** — Also provides an LLM agent skill

## Architecture

See [docs/architecture.md](./docs/architecture.md) for the ecosystem overview.

## Development

See [CONTRIBUTING.md](./CONTRIBUTING.md) for development guidelines.

## License

This project is licensed under the [MIT License](./LICENSE).
