# Home Infrastructure IaC

This repository contains the **Infrastructure as Code (IaC)** setup for my home IT infrastructure.

## Project Structure

- `inventories/` – Ansible inventories for production and test environments
- `roles/` – Reusable Ansible roles (common, proxmox, kubernetes.cluster)
- `playbooks/` – Main playbooks to deploy and configure infrastructure
- `vault/` – Encrypted secrets for Proxmox and other services
- `collections/` – Any custom Ansible collections used
- `cache/` – Cached facts and temporary files (ignored by Git)

## Vault

- `.vault-pass` – Password file for decrypting vault (ignored by Git)
- `vault/vault.yaml` – Encrypted secrets (Proxmox root password, etc.)

## Usage

1. Make sure `.vault-pass` exists and contains the Vault password.
2. Run playbooks using:

```bash
ansible-playbook playbooks/site.yaml --vault-password-file .vault-pass


## Playbooks
### proxmox node setup
Files:
```bash
inventories/hosts.yaml
playbooks/proxmox_node_setup.yaml
roles/proxmox/node/tasks/main.yaml
roles/proxmox/node/handlers/main.yaml
roles/proxmox/node/templates/motd.j2
vault/hosts_vault.yaml
```
Run:
```bash
ansible-playbook -i inventories/hosts.yaml playbooks/proxmox_node_setup.yaml
```

