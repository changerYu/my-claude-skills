# my-claude-skills

我的個人 Claude Code skills 集合。

## 安裝

```bash
claude plugin install https://github.com/silve/my-claude-skills
```

## 包含的 Skills

| Skill | 說明 | 使用方式 |
|-------|------|---------|
| `example-skill` | 生成程式碼摘要 | `/example-skill src/index.ts` |

## 新增 Skill

在 `skills/` 下建立新資料夾，加入 `SKILL.md`：

```
skills/
└── my-new-skill/
    ├── SKILL.md        # 必要：skill 主體指令
    └── templates/      # 選用：附帶模板或參考資料
```

`SKILL.md` 最小格式：

```markdown
---
name: my-new-skill
description: 說明這個 skill 做什麼
disable-model-invocation: true
---

# 指令內容

$ARGUMENTS
```

## Skill 設定參考

| Frontmatter | 效果 |
|------------|------|
| `disable-model-invocation: true` | 只有使用者可用 `/skill-name` 呼叫 |
| `user-invocable: false` | 只有 Claude 自動觸發（背景知識） |
| `context: fork` | 在獨立子 agent 中執行 |
| `allowed-tools: Read, Grep` | 限制可用工具 |
