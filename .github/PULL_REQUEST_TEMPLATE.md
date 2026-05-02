## Description

<!-- What does this PR do? Link relevant issues. -->

Fixes #

## Type of Change

- [ ] `feat`: New feature (new submodule)
- [ ] `fix`: Bug fix
- [ ] `docs`: Documentation
- [ ] `refactor`: Code restructuring
- [ ] `perf`: Performance improvement
- [ ] `test`: Tests
- [ ] `chore`: Maintenance (submodule updates)
- [ ] Breaking change (add `!` after type or `BREAKING CHANGE:` in footer)

## Checklist

- [ ] Commits follow [Conventional Commits](https://www.conventionalcommits.org/)
- [ ] [CHANGELOG.md](./CHANGELOG.md) updated under `[Unreleased]`
- [ ] Submodule changes pushed to their respective repos first
- [ ] Documentation updated (if applicable)

## How to Validate

### Automated checks

- [ ] CI passes

### Manual verification

1. Clone with submodules: `git clone --recurse-submodules https://github.com/TheSmuks/pike-dev.git`
2. Verify submodule is properly initialized

### Edge cases to consider

- Submodule references should point to valid commits
- Update submodule before updating hub repo
