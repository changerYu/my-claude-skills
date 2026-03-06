---
name: example-skill
description: 範例 skill：根據輸入的檔案路徑生成程式碼摘要。示範 skill 的基本結構，包含引數傳遞與模板使用。
disable-model-invocation: true
---

# 程式碼摘要

為以下路徑的檔案生成摘要：$ARGUMENTS

## 步驟

1. 讀取目標檔案內容
2. 識別主要函式、類別、與邏輯區塊
3. 使用 [templates/summary-template.md](templates/summary-template.md) 的格式輸出摘要
4. 最後列出任何潛在問題或改善建議
