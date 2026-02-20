# Step 1: Creating LXC Container for Minecraft + Crafty

**Date:** 2026-02-20
**Tags:** proxmox, lxc, minecraft, crafty

## Container Configuration Decision

| Setting | Choice | Reason |
|---------|--------|--------|
| **Unprivileged** | ✅ CHECKED | Security isolation from host - if container compromised, host stays safe |
| **Nesting** | ✅ CHECKED | Required for running Docker inside LXC (Crafty runs in Docker) |

## Why These Settings Matter

- **Unprivileged**: Maps root in container to unprivileged user on host (UID 100000+)
- **Nesting**: Allows Docker to create its own containers (containers inside containers)

# Step 2: General Tab Configuration

## Settings Applied
- **CT ID:** 102
- **Hostname:** minecraft-crafty
- **Unprivileged:** Yes
- **Nesting:** Yes

## Why Nesting Is Available
In Proxmox 9.1.1, nesting is only available when unprivileged is checked. This is intentional - privileged + nesting is considered too dangerous for the UI to allow.

# Step 3: Template Selection

## Template Chosen
- **OS:** Ubuntu 24.04 LTS
- **Why:** Stable, well-supported, familiar from previous setup

# Step 4: Disk Allocation

## Disk Size
- **Allocated:** 20GB
- **Why:** 
  - Minecraft worlds grow over time
  - Crafty stores server files, backups, logs
  - Room for plugins/mods
  - Docker images take space

# Step 5: CPU Allocation

## Cores Allocated
- **4 cores** out of 6 total on host
- **Reasoning:**
  - Minecraft server benefits from multiple cores
  - Crafty itself is lightweight
  - Leaves 2 cores for Proxmox and other containers

# Step 6: Memory Allocation

## RAM Allocation
- **6GB (6144 MiB)** to container
- **1GB (1024 MiB)** swap

## Why 6GB?
| Component | Estimated RAM |
|-----------|---------------|
| Crafty Controller | 200-500 MB |
| Minecraft server | 2-4 GB (depends on players/plugins) |
| Docker overhead | ~200 MB |
| **Total recommended** | **4-6 GB** |

## Swap
- 1GB as safety net if Minecraft memory spikes
- Not ideal (slower than RAM), but prevents crashes

# Step 7: Network Configuration

## Settings
- **Bridge:** vmbr0 (default Proxmox bridge)
- **IPv4:** DHCP (will get IP from router)

## Why DHCP?
- Simplest setup for now
- Can set static IP later if needed
- IP will be in same subnet as other containers (192.168.0.x)

## Ports We'll Use Later
| Port | Purpose |
|------|---------|
| 8000 | Crafty Web UI (HTTP) |
| 8443 | Crafty Web UI (HTTPS) |
| 25565 | Default Minecraft Java server |
| 19132 | Bedrock Edition (UDP) |

# Step 8: DNS Configuration

## Settings
- **DNS:** Use host settings (default)
- This inherits DNS from Proxmox host

# Step 9: Container Creation

**Date:** 2026-02-20

## Final Configuration Summary

| Tab | Setting | Value |
|-----|---------|-------|
| General | CT ID | 103 |
| | Hostname | minecraft-crafty |
| | Unprivileged | Yes |
| | Nesting | Yes |
| Template | OS | Ubuntu 24.04 |
| Disks | Root Disk | 20GB |
| CPU | Cores | 4 |
| Memory | RAM | 6GB (6144 MiB) |
| | Swap | 1GB (1024 MiB) |
| Network | Bridge | vmbr0 |
| | IPv4 | DHCP |

## Status
✅ Container configuration complete
⏳ Container created (clicking Finish)
