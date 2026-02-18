# Step 3: Complete LXC Container Configuration

**Date:** 2026-02-18
**Template:** Ubuntu 24.04 LTS

## Final Container Settings

| Tab | Setting | Value |
|-----|---------|-------|
| **General** | CT ID | 101 |
| | Hostname | notex-ai |
| | Unprivileged | Yes |
| | Nesting | Yes |
| **Template** | OS | Ubuntu 24.04 standard |
| **Disks** | Root Disk | 20GB |
| **CPU** | Cores | 4 |
| **Memory** | RAM | 4GB (4096 MiB) |
| | Swap | 1GB (1024 MiB) |
| **Network** | Bridge | vmbr0 |
| | IPv4 | DHCP |
| **DNS** | | Use host settings |

## Resource Allocation Reasoning
- **4 CPU cores**: Leaves 2 cores for Proxmox host
- **4GB RAM**: Enough for small AI models (3B parameters)
- **20GB disk**: Sufficient for OS, Ollama, Notex, and course materials

## Status
✅ Container created
⏳ Starting container (next step)
