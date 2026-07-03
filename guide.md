# OpenCode Configuration Guide

## Configuration File Locations

- **Global Config**: `~/.config/opencode/opencode.json` (Windows: `C:\Users\<username>\.config\opencode\opencode.json`)
- **Project Config**: `opencode.json` in project root directory

## Adding Auto Agent

```json
{
  "agent": {
    "auto": {
      "description": "Auto agent with write, edit, and bash tools.",
      "tools": {
        "write": true,
        "edit": true,
        "bash": true,
        "read": true,
        "grep": true,
        "glob": true
      },
      "permission": {
        "write": "allow",
        "edit": "allow",
        "bash": "allow"
      }
    }
  }
}
```

### Tools Description

| Tool | Description |
|------|-------------|
| `write` | Write files |
| `edit` | Edit files |
| `bash` | Execute shell commands |
| `read` | Read files |
| `grep` | Content search |
| `glob` | File pattern matching |

## Setting Global Permissions

```json
{
  "permission": {
    "edit": "allow",
    "bash": "allow",
    "read": "allow",
    "glob": "allow",
    "grep": "allow"
  }
}
```

## Setting Auto Compaction

```json
{
  "compaction": {
    "auto": true
  }
}
```

## Complete Configuration Example

```json
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {},
  "mcp": {},
  "agent": {
    "auto": {
      "description": "Auto agent with write, edit, and bash tools.",
      "tools": {
        "write": true,
        "edit": true,
        "bash": true,
        "read": true,
        "grep": true,
        "glob": true
      },
      "permission": {
        "write": "allow",
        "edit": "allow",
        "bash": "allow"
      }
    }
  },
  "permission": {
    "edit": "allow",
    "bash": "allow",
    "read": "allow",
    "glob": "allow",
    "grep": "allow"
  },
  "compaction": {
    "auto": true
  }
}
```

## Configuration Priority

1. Project config (`./opencode.json`) - Applies only to current project
2. Global config (`~/.config/opencode/opencode.json`) - Applies to all projects

## Common Commands

```bash
# View current configuration
opencode config

# Restart opencode to apply changes
# Configuration changes require restarting opencode
```
