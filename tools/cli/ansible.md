# Ansible Cheat-Sheet

## Ad-hoc Commands

| Command | Description |
| --- | --- |
| `ansible all -m ping` | Ping all hosts in the inventory |
| `ansible all -m ping -i inventory.ini` | Use a specific inventory file |
| `ansible web -m ping` | Target only the `web` group |
| `ansible all -a "uptime"` | Run a shell command on all hosts (command module) |
| `ansible all -m shell -a "df -h"` | Run a command through the shell |
| `ansible all -m setup` | Gather all facts about the hosts |
| `ansible all -m setup -a "filter=ansible_distribution*"` | Gather a subset of facts |
| `ansible all -b -m apt -a "name=nginx state=present"` | Install a package with privilege escalation |
| `ansible all --list-hosts` | Show which hosts a pattern matches |

## Inventory

| Command | Description |
| --- | --- |
| `ansible-inventory --list` | Dump the full inventory as JSON |
| `ansible-inventory --graph` | Show inventory as a tree of groups and hosts |
| `ansible-inventory --host <host>` | Show variables for a single host |
| `ansible all -i "host1,host2," -m ping` | Use an inline comma-separated inventory |

## Running Playbooks

| Command | Description |
| --- | --- |
| `ansible-playbook site.yml` | Run a playbook |
| `ansible-playbook site.yml -i inventory.ini` | Run with a specific inventory |
| `ansible-playbook site.yml --check` | Dry-run without making changes |
| `ansible-playbook site.yml --diff` | Show file/content changes as they happen |
| `ansible-playbook site.yml --check --diff` | Dry-run and preview the diffs |
| `ansible-playbook site.yml -l web` | Limit execution to a host or group |
| `ansible-playbook site.yml -t deploy` | Only run tasks with the `deploy` tag |
| `ansible-playbook site.yml --skip-tags cache` | Skip tasks with a given tag |
| `ansible-playbook site.yml --start-at-task "Copy config"` | Start execution at a specific task |
| `ansible-playbook site.yml --step` | Confirm each task interactively |
| `ansible-playbook site.yml --list-tasks` | List all tasks without running them |
| `ansible-playbook site.yml --list-tags` | List all tags in the playbook |
| `ansible-playbook site.yml --syntax-check` | Validate playbook syntax |

## Privilege Escalation and Connection

| Command | Description |
| --- | --- |
| `ansible-playbook site.yml -b` | Become root (privilege escalation) |
| `ansible-playbook site.yml -b -K` | Become root and prompt for the become password |
| `ansible-playbook site.yml -u deploy` | Connect as a specific SSH user |
| `ansible-playbook site.yml -k` | Prompt for the SSH connection password |
| `ansible-playbook site.yml --private-key=~/.ssh/id_rsa` | Use a specific SSH private key |
| `ansible all -m ping -f 20` | Set the number of parallel forks |

## Variables

| Command | Description |
| --- | --- |
| `ansible-playbook site.yml -e "env=prod"` | Pass an extra variable via CLI |
| `ansible-playbook site.yml -e @vars.yml` | Load extra variables from a file |
| `ansible-playbook site.yml -vvv` | Increase verbosity for debugging |

## Ansible Vault

| Command | Description |
| --- | --- |
| `ansible-vault create secrets.yml` | Create a new encrypted file |
| `ansible-vault edit secrets.yml` | Edit an encrypted file |
| `ansible-vault view secrets.yml` | View an encrypted file |
| `ansible-vault encrypt vars.yml` | Encrypt an existing file |
| `ansible-vault decrypt vars.yml` | Decrypt a file |
| `ansible-vault rekey secrets.yml` | Change the vault password |
| `ansible-playbook site.yml --ask-vault-pass` | Prompt for the vault password at runtime |
| `ansible-playbook site.yml --vault-password-file .vault_pass` | Read the vault password from a file |

## Galaxy (Roles and Collections)

| Command | Description |
| --- | --- |
| `ansible-galaxy init myrole` | Scaffold a new role skeleton |
| `ansible-galaxy install geerlingguy.nginx` | Install a role from Galaxy |
| `ansible-galaxy install -r requirements.yml` | Install roles/collections from a requirements file |
| `ansible-galaxy collection install community.general` | Install a collection |
| `ansible-galaxy role list` | List installed roles |
| `ansible-galaxy collection list` | List installed collections |

## Documentation and Config

| Command | Description |
| --- | --- |
| `ansible-doc <module>` | Show documentation for a module |
| `ansible-doc -l` | List all available modules |
| `ansible-config dump` | Show the current effective configuration |
| `ansible-config dump --only-changed` | Show only non-default settings |
| `ansible --version` | Show version and config file paths |
