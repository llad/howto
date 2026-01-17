# howto (Codex CLI helper)

This directory provides a small `howto` helper that turns a natural-language request into a single shell command via the Codex CLI. It supports two modes:

- **Executed**: `howto "describe the command"` prints a suggested command.
- **Sourced**: enables an interactive wrapper and a readline key binding for bash.

## Requirements

- Bash
- Codex CLI available on `PATH` (the `howto` script runs `codex exec`)

## Installation

1) Put `howto` on your `PATH` (for example, `~/.local/bin/howto`).
2) Source it from your bash startup file to enable the interactive features.

Add this to `~/.bashrc`:

```bash
# howto interactive wrapper + readline binding
if [ -f "$HOME/.local/bin/howto" ]; then
  . "$HOME/.local/bin/howto"
fi
```

Then reload your shell:

```bash
source ~/.bashrc
```

## Usage

### CLI mode (prints a command)

```bash
howto "find all JSON files and count them"
```

### Interactive mode (with prompt + history)

```bash
howto "list big files in this directory"
```

This will:
- Generate a suggested command
- Pre-fill it for editing
- Execute the command you accept

### Readline shortcut (Ctrl+G)

In an interactive bash session:
- Type a natural-language request on the command line.
- Press `Ctrl+G`.
- The line is replaced with the suggested command.

## Notes

- The sourced mode is bash/readline specific.
- `howto -p` is used internally to request “print only” output from the CLI mode.
