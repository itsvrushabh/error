# tmux Guide

## Config Locations

- **Primary config**: `~/.tmux.conf` or `~/.config/tmux/tmux.conf`
- **Plugins (TPM)**: `~/.tmux/plugins/` or `~/.config/tmux/plugins/`

## Common Tasks & Fixes

### 1. Reloading Config
```bash
tmux source-file ~/.tmux.conf
# or ~/.config/tmux/tmux.conf
```

### 2. TPM (Tmux Plugin Manager)
- **Install plugins**: `prefix + I`
- **Update plugins**: `prefix + U`
- **Clean unused plugins**: `prefix + alt + u`

### 3. Debugging Custom Scripts (e.g., `tmux-whisper`)
- Run the script directly in Bash outside tmux to see full `stderr` and exit codes.
- Check `run-shell` or `display-message` output inside tmux.
- Verify environment variables inside tmux: `tmux show-environment`

### 4. Stale Server / Socket
If tmux hangs or refuses connections:
```bash
tmux ls
tmux kill-server   # Warning: closes all active sessions
```
