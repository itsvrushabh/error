# WSL System Guide

## Config Locations

- **Distro config (inside WSL)**: `/etc/wsl.conf`
- **Global WSL2 VM config (on Windows)**: `C:\Users\<User>\.wslconfig`

## Common Tasks & Fixes

### 1. Enable `systemd` in WSL
In `/etc/wsl.conf`:
```ini
[boot]
systemd=true
```
Then restart WSL from PowerShell/CMD:
```powershell
wsl --shutdown
```

### 2. Service & Journal Diagnostics
```bash
systemctl --failed
systemctl status <service>
journalctl -xeu <service>
```

### 3. DNS / Networking Issues
- Check `/etc/resolv.conf` and test `curl -I https://github.com`.
- If corporate VPN or Windows DNS breaks WSL resolution, configure `[network] generateResolvConf = false` in `/etc/wsl.conf` and set custom nameservers in `/etc/resolv.conf`.

### 4. Filesystem & Interop
- Keep codebases in `/home/<user>/` (ext4) rather than `/mnt/c/` (9P) for speed and proper file permissions.
- Check interop (`explorer.exe .`, `clip.exe`) if Windows binaries fail to launch: ensure `[interop] enabled=true` in `/etc/wsl.conf`.
