# Step 10: First Start and Login

**Date:** 2026-02-20

## Starting the Container
1. Selected container 102
2. Clicked **Start** button
3. Waited for status to turn green
4. Clicked **Console** to access

## First Login

## Initial Commands
```bash
# Check Ubuntu version
cat /etc/os-release
PRETTY_NAME="Ubuntu 24.04 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo


# Check resources
free -h
               total        used        free      shared  buff/cache   available
Mem:           6.0Gi        30Mi       5.7Gi       104Ki       264Mi       6.0Gi
Swap:          1.0Gi          0B       1.0Gi

df -h
Filesystem                        Size  Used Avail Use% Mounted on
/dev/mapper/pve-vm--102--disk--0   20G  667M   18G   4% /
none                              492K  4.0K  488K   1% /dev
efivarfs                          150K   86K   60K  59% /sys/firmware/efi/efivars
tmpfs                             3.8G     0  3.8G   0% /dev/shm
tmpfs                             1.6G  100K  1.6G   1% /run
tmpfs                             5.0M     0  5.0M   0% /run/lock

# Update package list
apt update
