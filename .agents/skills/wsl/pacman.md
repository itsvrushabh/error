# Arch Linux (`pacman` & AUR) Guide

## Config Locations

- **Pacman config**: `/etc/pacman.conf`
- **Mirrorlist**: `/etc/pacman.d/mirrorlist`
- **AUR helpers**: `yay` or `paru`

## Common Tasks & Fixes

### 1. System Update
```bash
sudo pacman -Syu
```
*(Never run `pacman -Sy <pkg>` without `-u`—partial upgrades break shared libraries.)*

### 2. Keyring / Signature Errors
If `pacman` fails with `signature from ... is marginal trust` or `invalid or corrupted package (PGP signature)`:
```bash
sudo pacman -Sy archlinux-keyring
sudo pacman-key --init
sudo pacman-key --populate archlinux
```

### 3. Database Lock Error
If `unable to lock database` appears (and no `pacman` process is actually running):
```bash
ps aux | grep pacman
sudo rm /var/lib/pacman/db.lck
```

### 4. AUR Packages (`yay` / `paru`)
- Rebuild AUR packages after major library updates (e.g., Python, ICU, OpenSSL).
- Inspect `PKGBUILD` before installing untrusted AUR packages.
