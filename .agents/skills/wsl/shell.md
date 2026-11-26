# Shell Guide (Bash / Zsh)

## Config Locations

- **Bash**: `~/.bashrc`, `~/.bash_profile`, `~/.profile`
- **Zsh**: `~/.zshrc`, `~/.zprofile`, `~/.zshenv`
- **Shared env**: `~/.config/environment.d/*.conf` (when `systemd` is enabled)

## Common Tasks & Fixes

### 1. Reloading Configuration
```bash
source ~/.bashrc   # or exec bash -l
```

### 2. Debugging Scripts & Startup
- **Syntax check**: `bash -n script.sh`
- **Trace execution**: `bash -x script.sh`
- **Linting**: `shellcheck script.sh`
- **Find where a command comes from**: `type -a <cmd>` or `which <cmd>`

### 3. `PATH` Issues
- Inspect `PATH` cleanly: `echo "$PATH" | tr ':' '\n'`
- Always append/prepend safely in `~/.bashrc`:
  ```bash
  export PATH="$HOME/.local/bin:$PATH"
  ```
- Avoid Windows `PATH` pollution in WSL if it causes slowdowns or conflicts (configured in `/etc/wsl.conf` under `[interop] appendWindowsPath = false`).
