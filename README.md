# Ansible Role for RHEL
A role for configuring common system settings for RHEL-based systems

## Tasks
- Update system and install basic packages
- Reduce bootloader wait time from 5s to 1s (grub)
- Automated security updates (dnf-automatic)
- SSH keys for root user
- NTP server (chrony)
- Enforce SELinux
- Create swapfile

## Variables
Variables for configuration are provided in vars/main.yml:
```
---
packages:
  - net-tools
  - bind-utils
  - vim
  - zip
  - unzip
ssh_root_keys: |
  ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIBGg14O1peHu4eD1AC2m+VH1n0kGAl0hwXzeMFuhxxv6
ntp_enabled: true
ntp_servers: |
  server time.cloudflare.com
selinux_policy: targeted
selinux_state: enforcing
swapfile_enabled: true
swapfile_size: 2048M
autoupdate_enabled: true
autoupdate_type: security
grub_timeout: 1
```
