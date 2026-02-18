# Tests

## Prerequisites

- Python >= 3.12
- [uv](https://docs.astral.sh/uv/)

## Development environment (uv)

From the collection root:

```bash
# Create venv and install test/lint dependencies (dependency-groups.dev in pyproject.toml)
uv sync
```

## Lint

From the collection root (after `uv sync`):

```bash
uv run task lint       # ansible-lint
uv run task yamllint   # yamllint
```

## Molecule tests

Requires Docker:

```bash
uv run task test
```

## Syntax check

With the collection on the path (e.g. after `ansible-galaxy collection build` and install, or `ANSIBLE_COLLECTIONS_PATHS=.`):

```bash
ansible-playbook -i tests/inventory tests/test_fluentbit.yml --syntax-check
```

## Check mode (dry run)

Requires a real target host in `tests/inventory`:

```bash
ansible-playbook -i tests/inventory tests/test_fluentbit.yml --check -l <host>
```

## Full run

Only on a host where you intend to install Fluent Bit:

```bash
ansible-playbook -i tests/inventory tests/test_fluentbit.yml -l <host>
```
