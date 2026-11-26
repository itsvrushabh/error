# Starship Prompt Guide

## Config Location

- **Config file**: `~/.config/starship.toml`
- **Shell init** (in `~/.bashrc`):
  ```bash
  eval "$(starship init bash)"
  ```

## Common Tasks & Fixes

### 1. Diagnostics & Timings
If the prompt feels slow (common in `/mnt/c/` on WSL):
```bash
starship timings
```
- Increase timeout if needed in `~/.config/starship.toml`:
  ```toml
  command_timeout = 1000
  ```

### 2. Missing Icons / Garbled Characters
- Ensure a **Nerd Font** (e.g., JetBrainsMono Nerd Font, CaskaydiaCove Nerd Font) is installed on **Windows** and selected in Windows Terminal / your terminal emulator.

### 3. Config Validation
```bash
starship print-config
```
