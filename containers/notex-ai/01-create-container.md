# Step 1: Creating LXC Container for Notex

**Date:** 2026-02-18
**Tags:** proxmox, lxc, container, notex

## Container Configuration
- **CT ID:** 101
- **Hostname:** notex-ai
- **Unprivileged:** Yes (for security)
- **Nesting:** Yes (required for Docker/Ollama)

## Why These Settings
- **Unprivileged container**: Maps root in container to unprivileged user on host - if container is compromised, host stays safe
- **Nesting enabled**: Allows running Docker/Ollama inside the container

## Screenshot

## Status
✅ General tab configured
⏳ Template selection (next step)
