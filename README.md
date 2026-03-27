# my-claude-skills

個人 Claude Code skills 管理 repo。

## 新增 skill

每個 skill 放在獨立子資料夾，資料夾名即 skill 名稱：

```
my-claude-skills/
└── skill-name/
    └── SKILL.md
```

新增後：

```bash
git add . && git commit -m "add skill-name" && git push
```

---

## 新電腦安裝步驟

### Windows（cmd）

```cmd
git clone git@github.com:changerYu/my-claude-skills.git %USERPROFILE%\my-claude-skills
mkdir %USERPROFILE%\.claude\plugins\marketplaces
mklink /J %USERPROFILE%\.claude\plugins\marketplaces\my-claude-skills %USERPROFILE%\my-claude-skills
```

### Windows（PowerShell）

```powershell
git clone git@github.com:changerYu/my-claude-skills.git "$env:USERPROFILE\my-claude-skills"
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\plugins\marketplaces"
New-Item -ItemType Junction -Path "$env:USERPROFILE\.claude\plugins\marketplaces\my-claude-skills" -Target "$env:USERPROFILE\my-claude-skills"
```

### WSL / Linux / macOS

```bash
git clone git@github.com:changerYu/my-claude-skills.git ~/my-claude-skills
mkdir -p ~/.claude/plugins/marketplaces
ln -s ~/my-claude-skills ~/.claude/plugins/marketplaces/my-claude-skills
```

---

## 安裝後設定（所有環境）

在 `~/.claude/settings.json` 的 `extraKnownMarketplaces` 加入：

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

重啟 Claude Code。
