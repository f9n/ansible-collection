# Development

## Install from source

```bash
ansible-galaxy collection build
ansible-galaxy collection install f9n-general-*.tar.gz -f
```

## Testing and linting

The project uses [uv](https://docs.astral.sh/uv/) for test and lint dependencies.

**Prerequisites:** Python >= 3.12, [uv](https://docs.astral.sh/uv/).

```bash
# Create venv and install test/lint dependencies (from pyproject.toml)
uv sync

# Lint
uv run task lint       # ansible-lint
uv run task yamllint   # yamllint

# Molecule tests (requires Docker)
uv run task test
```

Commit `uv.lock` for reproducible installs. To refresh the lockfile: `uv lock`.

See [tests/README.md](tests/README.md) for playbook syntax check, check mode, and full run.
