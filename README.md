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
