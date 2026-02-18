## 🐛 Troubleshooting: Missing zstd

### The Error
When running the Ollama install script, I got:

root@notex-ai:~# curl -fsSL https://ollama.com/install.sh | sh
>>> Installing ollama to /usr/local
ERROR: This version requires zstd for extraction. Please install zstd and try again:
  - Debian/Ubuntu: sudo apt-get install zstd
  - RHEL/CentOS/Fedora: sudo dnf install zstd
  - Arch: sudo pacman -S zstd


### The Fix
```bash
apt install -y zstd

### Continued with
root@notex-ai:~# curl -fsSL https://ollama.com/install.sh | sh


root@notex-ai:~# ollama pull phi3:3.8b-mini-128k-instruct-q4_0 
pulling manifest 
pulling 633fc5be925f: 100% ▕██████████████████████████████▏ 2.2 GB                         
pulling fa8235e5b48f: 100% ▕██████████████████████████████▏ 1.1 KB                         
pulling 542b217f179c: 100% ▕██████████████████████████████▏  148 B                         
pulling 8dde1baf1db0: 100% ▕██████████████████████████████▏   78 B                         
pulling 23291dc44752: 100% ▕██████████████████████████████▏  483 B                         
verifying sha256 digest 
writing manifest 
success 

