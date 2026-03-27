# my-claude-skills

我的個人 Claude Code skills 集合。

## 用途

統一管理自訂的 Claude Code slash commands（skills），方便在不同電腦間同步使用。

---

## 在新電腦上安裝

```bash
# 1. Clone repo
git clone git@github.com:changerYu/my-claude-skills.git ~/my-claude-skills

# 2. 建立 symlink 掛載到 Claude Code
mkdir -p ~/.claude/plugins/marketplaces
ln -s ~/my-claude-skills ~/.claude/plugins/marketplaces/my-claude-skills
```

然後在 `~/.claude/settings.json` 的 `extraKnownMarketplaces` 加入：

```json
{
  "extraKnownMarketplaces": {
    "my-claude-skills": {
      "source": {
        "source": "directory",
        "path": "~/.claude/plugins/marketplaces/my-claude-skills"
      }
    }
  }
}
```

重啟 Claude Code 即生效。

---

## 新增 Skill 後同步

```bash
cd ~/my-claude-skills
git add .
git commit -m "add skill-name"
git push
```

---

## Skills 目錄

每個 skill 放在獨立子資料夾，資料夾名即 skill 名稱：

```
my-claude-skills/
└── skills/
    └── my-new-skill/
        └── SKILL.md
```

`SKILL.md` 基本格式：

```markdown
---
name: my-new-skill
description: 說明這個 skill 做什麼
---

# 指令內容

$ARGUMENTS
```
