---
name: dev-env-troubleshoot
description: >-
  Troubleshooting and error-handling guide for WSL, Arch Linux, Neovim (nvim),
  tmux, Bash, and related CLI tools. Use when diagnosing or fixing environment,
  shell, editor, or multiplexer errors.
---

# Dev Environment Troubleshooting Skill

A structured runbook for diagnosing and resolving common errors across **WSL**, **Arch Linux**, **Neovim**, **tmux**, and **Bash**.

## General Triage Workflow

1. **Capture the exact error**: Note the full error message, exit code (`echo $?`), and command/context that triggered it.
2. **Isolate the layer**: Determine whether the issue is in the shell (Bash), multiplexer (tmux), editor (nvim), distro (Arch), or host/VM boundary (WSL).
3. **Check logs & health**: Inspect relevant logs or built-in diagnostics before making changes.

---

## 1. WSL (Windows Subsystem for Linux)

- **Systemd / services**: Check `systemctl status` and `/etc/wsl.conf` (`[boot] systemd=true`).
- **Networking / DNS**: Inspect `/etc/resolv.conf` and test `curl -I https://github.com`. If DNS breaks, check `generateResolvConf` in `/etc/wsl.conf`.
- **Filesystem / Permissions**: Prefer Linux filesystem (`/home/...`) over `/mnt/c/...` for performance and POSIX permissions.
- **Restarting WSL**: From PowerShell/CMD: `wsl --shutdown` then reopen the distro.

## 2. Arch Linux

- **Package / Keyring errors**:
  - Refresh keys: `sudo pacman -Sy archlinux-keyring`
  - Sync & update: `sudo pacman -Syu`
- **AUR helpers (`yay` / `paru`)**: Rebuild packages if shared libraries updated.
- **Service failures**: `journalctl -xeu <service>` and `systemctl --failed`.

## 3. Neovim (`nvim`)

- **First step**: Run `:checkhealth` inside `nvim` to spot missing providers, LSPs, or treesitter parsers.
- **Plugin / config errors**:
  - Start with minimal config: `nvim --clean` to confirm if the issue is in user config.
  - Check `:messages` for Lua stack traces.
- **LSP issues**: Run `:LspInfo` and check `:LspLog` for server startup failures.

## 4. tmux

- **Config reload**: `tmux source-file ~/.tmux.conf` (or `~/.config/tmux/tmux.conf`).
- **Plugin issues (TPM)**: Press `prefix + I` to install, `prefix + U` to update.
- **Custom scripts / `tmux-whisper`**:
  - Test the script directly in Bash outside tmux to see full stderr/exit codes.
  - Check `tmux display-message` or `run-shell` output.
- **Stale server**: `tmux kill-server` if sockets/env vars are stuck (note: closes all sessions).

## 5. Bash

- **Syntax / quoting**: Run `bash -n <script>` to check syntax, or `shellcheck <script>` if installed.
- **Trace execution**: Run `bash -x <script>` to see each expanded command.
- **PATH / environment**: Check `which <cmd>`, `type <cmd>`, and `env` to verify expected binaries and variables are loaded in `~/.bashrc` or `~/.bash_profile`.
