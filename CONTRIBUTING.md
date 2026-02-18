# Contributing

Thank you for your interest in contributing to this Ansible collection!

## How to contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feat/my-feature`)
3. Make your changes following the guidelines below
4. Open a pull request

## Development setup

Prerequisites: Python >= 3.12, [uv](https://github.com/astral-sh/uv)

```bash
uv sync
uv run ansible-galaxy collection install -r requirements.yml
```

## Code style

- Follow [Ansible best practices](https://docs.ansible.com/ansible/latest/tips_tricks/index.html)
- Use fully-qualified collection names (FQCN) for all module calls
- Use `ansible.builtin.*` for built-in modules
- Keep task names descriptive and in the imperative form
- Variable names must be prefixed with the role name (e.g. `fluentbit_`)

## Linting

All contributions must pass the following checks:

```bash
uv run task yamllint
uv run task linkt
```

## Changelog

Every user-facing change must include a changelog fragment under `changelogs/fragments/`.
Use the `antsibull-changelog` format:

```yaml
# changelogs/fragments/my-change.yml
minor_changes:
  - fluentbit - added support for X (https://github.com/f9n/ansible-collection/pull/NNN).
```

Fragment types: `release_summary`, `major_changes`, `minor_changes`, `breaking_changes`,
`deprecated_features`, `removed_features`, `security_fixes`, `bugfixes`, `known_issues`.

## Commit messages

Use [Conventional Commits](https://www.conventionalcommits.org/) format:

```
feat: add LimitNOFILE support for systemd override
fix: correct storage.backlog.mem_limit key name
docs: update fluentbit role README
```

## Testing

Before opening a PR, run a syntax check:

```bash
ansible-playbook -i tests/inventory tests/test_fluentbit.yml --syntax-check
```

For roles with Molecule scenarios:

```bash
cd roles/fluentbit
molecule test
```
