# Step 5: Container Initial State

**Date:** 2026-02-18

## System Information
```bash
# Ubuntu Version
$(cat /etc/os-release | grep PRETTY_NAME)
root@notex-ai:~# cat /etc/os-release 
PRETTY_NAME="Ubuntu 24.04.4 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.4 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo

# Memory
$(free -h)
root@notex-ai:~# free -h
               total        used        free      shared  buff/cache   available
Mem:           4.0Gi        30Mi       3.2Gi       108Ki       746Mi       4.0Gi
Swap:          1.0Gi          0B       1.0Gi

# Disk Usage
$(df -h)
root@notex-ai:~# df -h
Filesystem                        Size  Used Avail Use% Mounted on
/dev/mapper/pve-vm--101--disk--0   30G  915M   27G   4% /
none                              492K  4.0K  488K   1% /dev
efivarfs                          150K   86K   60K  59% /sys/firmware/efi/efivars
tmpfs                             3.8G     0  3.8G   0% /dev/shm
tmpfs                             1.6G  104K  1.6G   1% /run
tmpfs                             5.0M     0  5.0M   0% /run/lock

# Update package list
apt update

# Upgrade any packages (optional but recommended)
apt upgrade -y

# Install basic tools
apt install -y curl wget git nano

# Network
DHCP assigned IP
Can reach the internet (pinged google.com)

