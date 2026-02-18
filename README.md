# f9n.general Ansible Collection

General-purpose Ansible Collection for automation: logging (Fluent Bit), and more to come. Supports **Linux (Ubuntu/Debian)** and **Windows**.

Inspired by the structure of [ansible-collections/amazon.aws](https://github.com/ansible-collections/amazon.aws): one collection, multiple roles and use cases over time.

## Description

This collection provides roles and content to automate common setup and configuration tasks across different environments. Current focus:

- **Logging:** Fluent Bit installation and configuration (Linux & Windows).

Additional roles (agents, monitoring, security, etc.) can be added in future releases.

## Requirements

- **ansible-core** >= 2.20
- **Host OS:** Ubuntu 20.04+ (focal, jammy, noble), Debian 11+ (bullseye, bookworm), Windows Server 2022/2025
- **Windows targets:** [ansible.windows](https://galaxy.ansible.com/ansible/windows) and [community.windows](https://galaxy.ansible.com/community/windows) collections (installed automatically as dependency)

## Installation

Install the collection from Ansible Galaxy:

```bash
ansible-galaxy collection install f9n.general
```

You can also add it to a `requirements.yml` file and install with `ansible-galaxy collection install -r requirements.yml`:

```yaml
---
collections:
  - name: f9n.general
```

To upgrade to the latest version:

```bash
ansible-galaxy collection install f9n.general --upgrade
```

To install a specific version:

```bash
ansible-galaxy collection install f9n.general:==1.0.0
```

Or in `requirements.yml`:

```yaml
---
collections:
  - name: f9n.general
    version: "1.0.0"
```

### Install from source (development)

See [DEVELOPMENT.md](DEVELOPMENT.md).

## Included content

| Role       | Description |
|-----------|-------------|
| **fluentbit** | Install and configure Fluent Bit (Linux & Windows) |

More roles will be added in future releases.

