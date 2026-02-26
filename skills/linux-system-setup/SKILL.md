---
name: linux-system-setup
description: Set up a basic Linux development environment with essential tools and configurations
version: 1.0.0
metadata:
  skill_forge:
    domain: "linux"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [linux, setup, development, terminal]
    category: system-administration
---

# Linux System Setup

## When to Use
Setting up a new Linux machine for development work or when you need a standardized Linux environment with essential tools.

## Prerequisites
- Fresh Linux installation (Ubuntu, Debian, CentOS, or similar distribution)
- User account with sudo privileges
- Internet connection

## Procedure
1. Update system packages: `sudo apt update && sudo apt upgrade -y` (Debian/Ubuntu) or `sudo yum update -y` (CentOS/RHEL)
2. Install essential development tools: `sudo apt install build-essential curl wget git vim htop tree -y`
3. Configure Git with your details: `git config --global user.name "Your Name"` and `git config --global user.email "your.email@example.com"`
4. Install package manager for your language (e.g., Node.js): `curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash - && sudo apt install nodejs -y`
5. Set up SSH key for secure connections: `ssh-keygen -t ed25519 -C "your.email@example.com"`
6. Configure firewall basics: `sudo ufw enable && sudo ufw default deny incoming && sudo ufw default allow outgoing`
7. Create common directory structure: `mkdir -p ~/projects ~/scripts ~/bin`

## Verification
Check installations with `git --version`, `node --version`, `curl --version`, and `ls -la ~/.ssh/` to confirm SSH key creation.

## Pitfalls
- Different package managers across distributions (apt vs yum vs pacman)
- Firewall rules may block necessary services
- SSH key permissions must be correct (600 for private key)

## Sources
- https://www.linux.com/what-is-linux/
- https://www.linux.org/
- https://linuxmint.com/
- https://www.linuxfoundation.org/
- https://en.wikipedia.org/wiki/Linux