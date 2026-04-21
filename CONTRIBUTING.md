# Contributing

## Commit messages

This repo uses [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
to drive automated releases. Each commit (or PR title, when squash-merging) should follow:

    <type>[optional scope]: <description>

### Types that trigger a release

| Type | Effect | Example |
|------|--------|---------|
| `fix:` | Patch bump (2.3.0 → 2.3.1) | `fix: correct protection domain calculation` |
| `feat:` | Minor bump (2.3.0 → 2.4.0) | `feat: support multi-AD deployments` |
| `feat!:` or `BREAKING CHANGE:` in body | Major bump (2.3.0 → 3.0.0) | `feat!: rename node_count variable` |

### Other types (no version bump, still appears in changelog)

`docs:`, `chore:`, `refactor:`, `ci:`, `test:`, `perf:`, `build:`, `style:`

### How your commits end up in a release

You don't need to do anything special to cut a release — just pick the right type when
you write the commit or PR title. When your PR merges to `main`:

- Your message will appear in `CHANGELOG.md` on the next release, grouped by type.
- The next version number is computed automatically from all commit types accumulated
  since the last release (any `feat:` → minor bump; otherwise patch).
- Maintainers publish releases by merging a separate "Release PR" that the automation
  keeps up to date.
