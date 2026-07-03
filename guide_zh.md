# OpenCode 配置指南

## 配置文件位置

- **全局配置**: `~/.config/opencode/opencode.json` (Windows: `C:\Users\<用户名>\.config\opencode\opencode.json`)
- **项目配置**: 项目根目录下的 `opencode.json`

## 添加 Auto Agent

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

### Tools 说明

| 工具 | 说明 |
|------|------|
| `write` | 写入文件 |
| `edit` | 编辑文件 |
| `bash` | 执行命令行命令 |
| `read` | 读取文件 |
| `grep` | 内容搜索 |
| `glob` | 文件模式匹配 |

## 设置全局权限

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

## 设置自动压缩

```json
{
  "compaction": {
    "auto": true
  }
}
```

## 完整配置示例

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

## 配置项优先级

1. 项目配置 (`./opencode.json`) - 仅对当前项目生效
2. 全局配置 (`~/.config/opencode/opencode.json`) - 对所有项目生效

## 常用命令

```bash
# 查看当前配置
opencode config

# 重启 opencode 使配置生效
# 配置修改后需要重启 opencode
```
