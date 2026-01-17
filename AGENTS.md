# AGENTS.md

## Overview
This folder contains the `howto` bash script. It runs as a CLI when executed and registers an interactive wrapper + readline key binding when sourced from `.bashrc`.

## Files
- `howto`: The single-file bash script (CLI + sourced mode).

## Expectations for edits
- Keep the script bash-only and compatible with `/usr/bin/env bash`.
- Preserve dual-mode behavior:
  - Executed: prints a single command line.
  - Sourced: enables the interactive wrapper and Ctrl+G binding.
- Avoid non-ASCII characters unless already present.
- Keep comments concise and focused on non-obvious behavior.

## Setup (for users)
Add this to `~/.bashrc`:

```bash
# howto interactive wrapper + readline binding
if [ -f "$HOME/.local/bin/howto" ]; then
  . "$HOME/.local/bin/howto"
fi
```

Reload:

```bash
source ~/.bashrc
```
