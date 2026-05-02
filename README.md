<div align="center">
  <h1>pike-dev</h1>
  <p><strong>Everything you need to build with Pike.</strong></p>
  <p>A unified hub for the Pike development toolchain — version management, language tooling, testing, and AI-assisted development.</p>
</div>

## Badges

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![11 Projects](https://img.shields.io/badge/Projects-11-brightgreen)](https://github.com/TheSmuks)
[![Pike 8.0+](https://img.shields.io/badge/Pike-8.0%2B-orange)](https://pike.lysator.liu.se/)
[![GitHub Stars](https://img.shields.io/github/stars/TheSmuks/pike-dev?style=social)](https://github.com/TheSmuks/pike-dev)

## Ecosystem

```mermaid
graph TD
    subgraph "Pike Language"
        P([Pike 8.0])
    end

    subgraph "Package & Version Management"
        PVM[pvm]
        PMP[pmp]
        EX[pmp-example-module]
    end

    subgraph "Language Tooling"
        PLS[pike-language-server]
        LSP[pike-lsp]
        TSP[tree-sitter-pike]
        AST[pike-ast]
    end

    subgraph "Developer Experience"
        INT[pike-introspect]
        PUNIT[punit-tests]
        CB[pike-cookbook]
    end

    subgraph "AI Support"
        KB[pike-ai-kb]
    end

    P --> PVM
    P --> PMP
    P --> LSP
    P --> PLS
    P --> AST

    PMP --> EX

    TSP --> PLS
    AST --> PLS
    INT --> PLS

    PUNIT --> P
    INT --> P

    LSP -.->|"deprecated"| PLS
    PLS -.->|"supersedes"| LSP
```

## Quick Start

Clone the entire ecosystem with one command:

```bash
git clone --recurse-submodules https://github.com/TheSmuks/pike-dev.git
cd pike-dev
```

Or initialize submodules after cloning:

```bash
git clone https://github.com/TheSmuks/pike-dev.git
cd pike-dev
git submodule update --init --recursive
```

Update all submodules to their latest versions:

```bash
git submodule update --remote
```

## Projects

### Language Tooling

[![pike-language-server](https://img.shields.io/badge/pike--language--server-active-brightgreen)](https://github.com/TheSmuks/pike-language-server)
Tier-3 LSP implementation for Pike — syntax highlighting, diagnostics, completions, hover

[![pike-ast](https://img.shields.io/badge/pike--ast-active-brightgreen)](https://github.com/TheSmuks/pike-ast)
Pure-Pike AST library — tokenization, parsing, querying, and pattern matching

[![tree-sitter-pike](https://img.shields.io/badge/tree--sitter--pike-active-brightgreen)](https://github.com/TheSmuks/tree-sitter-pike)
Tree-sitter grammar for Pike 8.0.1116 — syntax highlighting and AST queries

[![pike-lsp](https://img.shields.io/badge/pike--lsp-maintenance-yellow)](https://github.com/TheSmuks/pike-lsp)
Legacy LSP implementation — superseded by `pike-language-server`

### Package & Version Management

[![pvm](https://img.shields.io/badge/pvm-active-brightgreen)](https://github.com/TheSmuks/pvm)
Pike Version Manager — install, manage, and switch between Pike versions

[![pmp](https://img.shields.io/badge/pmp-active-brightgreen)](https://github.com/TheSmuks/pmp)
Package manager for Pike modules — install, version, and resolve dependencies

[![pmp-example-module](https://img.shields.io/badge/pmp--example--module-active-brightgreen)](https://github.com/TheSmuks/pmp-example-module)
Minimal example of a pmp-installable Pike module

### Developer Experience

[![punit-tests](https://img.shields.io/badge/punit--tests-active-brightgreen)](https://github.com/TheSmuks/punit-tests)
JUnit-inspired testing framework for Pike

[![pike-introspect](https://img.shields.io/badge/pike--introspect-active-brightgreen)](https://github.com/TheSmuks/pike-introspect)
Pike runtime introspection module — runtime symbol inspection and an LLM agent skill

[![pike-cookbook](https://img.shields.io/badge/pike--cookbook-active-brightgreen)](https://github.com/TheSmuks/pike-cookbook)
Complete Pike 8.0 programming cookbook with practical recipes and examples

### AI & LLM Support

[![pike-ai-kb](https://img.shields.io/badge/pike--ai--kb-active-brightgreen)](https://github.com/TheSmuks/pike-ai-kb)
Curated, runtime-verified knowledge base for Pike — 130+ stdlib modules, MCP server, agent skill

## Toolchain Flow

```
1. Install Pike      →  pvm (Pike Version Manager)
2. Manage deps      →  pmp (Pike Module Package Manager)
3. Develop          →  pike-language-server (LSP for IDE support)
4. Test             →  punit-tests (JUnit-style testing framework)
5. Debug            →  pike-introspect (runtime introspection)
6. AI Assist        →  pike-ai-kb (knowledge base + MCP tools)
```

<details>
<summary><strong>Contributing & Development</strong></summary>

## Contributing

Contributions are welcome. Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

## Development Setup

Each submodule is an independent repository. After cloning with submodules:

```bash
# Verify all submodules are present
ls -la repos/

# Update a specific submodule
cd repos/pike-language-server
git pull origin main
cd ../..
git add repos/pike-language-server
git commit -m "Update pike-language-server"
```

## Running Tests

```bash
# Run tests in a specific submodule
cd repos/pike-language-server
make test

# Run tests in all submodules
for repo in repos/*; do
  (cd "$repo" && make test 2>/dev/null) || echo "No test target: $repo"
done
```

</details>

<details>
<summary><strong>Adding New Submodules</strong></summary>

## Adding a New Submodule

1. **Create the repository** under [TheSmuks](https://github.com/TheSmuks)

2. **Add as a submodule** inside `repos/`:
   ```bash
   git submodule add https://github.com/TheSmuks/new-project.git repos/new-project
   ```

3. **Configure the submodule** (optional):
   ```bash
   cd repos/new-project
   git checkout main
   cd ..
   ```

4. **Commit the submodule reference**:
   ```bash
   git add repos/new-project
   git commit -m "Add new-project as a submodule"
   git push origin main
   ```

5. **Update this README**:
   - Add the project to the appropriate category under [Projects](#projects)
   - Update the ecosystem diagram
   - Update the toolchain flow if applicable

## Removing a Submodule

```bash
# Deinitialize the submodule
git submodule deinit -f repos/old-project

# Remove from index
git rm repos/old-project

# Remove the directory
rm -rf repos/old-project

# Commit
git commit -m "Remove old-project submodule"
```

## Submodule Best Practices

- Each submodule maintains its own git history, CI/CD, and release cycle
- The hub repo only tracks commit references via `.gitmodules`
- Always fetch and merge in the submodule before updating the hub reference
- Use annotated tags for releases; hub repo should track those tags

</details>

## Architecture

See [docs/architecture.md](./docs/architecture.md) for the full ecosystem overview, dependency graph, and inter-project relationships.

## License

This project is licensed under the [MIT License](./LICENSE).
