# CC 專家培養課程 v2 — 教師審計版

> 上一版問題：節奏過快、材料順序不當、產出過多、無緩衝、無反饋循環
> v2 修正：三階段真實項目驅動、先實踐後理論、內建回顧、可持續節奏

---

## 教師審計：v1 的問題

| 問題 | v1 | v2 修正 |
|------|-----|---------|
| 起步太快 | Day1 讀5個Skill | Day1-2 只讀+理解，不寫 |
| 源碼過早 | Day3 讀 loadSkillsDir.ts | 先親手寫過3個Skill，再讀源碼 |
| 架構在中間 | Cycle3 在Hook後 | 先實踐Hook，帶著問題學架構 |
| 產出過多 | 6天6張架構圖 | 每個架構圖配2-3天，邊用邊畫 |
| MCP 太壓縮 | Day21-22 兩天 | 獨立一週 |
| 無緩衝 | 30天連續 | 每7天1天回顧/緩衝 |
| 無反饋循環 | 寫完就過了 | 每階段回頭改進早期作品 |
| 驗收模糊 | "能說出..." | 驗收 = 能用 + 能改 + 能教 |

## 新的設計原則

1. **項目驅動**：每個階段圍繞一個真實項目，不是孤立練習
2. **螺旋深入**：同一主題在不同階段以不同深度重複出現
3. **先做後讀**：先動手體驗，再讀源碼理解原理
4. **回顧內建**：每階段結束回顧+改進早期作品
5. **可持續**：每天1h內可完成，每7天1天緩衝

---

## Phase 1 — 成為 Skill 開發者（第1-14天）

> 項目：構建一個個人 Skill Pack（5個Skill，你每天用的）
> 目標：能用 Skill 擴展 CC 的能力
> 驗收：你的 Skill Pack 被自己每天使用，且改進了3次以上

### Week 1 — 模仿與理解（第1-7天）

**Day 1-2：大量輸入**
- 讀 [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) 中的 10 個熱門 Skill
- 每個 Skill 回答：它解決什麼問題？frontmatter 每個欄位什麼作用？
- 產出：一張表 — Skill frontmatter 欄位 × 10個範例的實際值
- 不寫任何代碼。只觀察。

**Day 3-4：寫第一個 Skill**
- 選你今天用 CC 時最煩的一個重複操作
- 模仿你讀過的最好範例，寫 15-30 行
- 測試 `/your-skill`，改進，再測試
- 產出：第一個可用的 Skill

**Day 5-6：寫第二、第三個 Skill**
- 每個 Skill 解決一個具體問題
- 至少一個使用 `argumentHint` 接收參數
- 產出：3 個 Skill

**Day 7：回顧日**
- 對比你的 3 個 Skill 和 Day1-2 讀的 10 個範例
- 找出差距，列出改進點
- 改進你的 3 個 Skill
- 不學新東西。只回顧和改進。

### Week 2 — 理解與深化（第8-14天）

**Day 8-9：Skill 是怎麼工作的**
- 材料：CC 源碼 `src/skills/loadSkillsDir.ts`（帶著問題讀：我寫的 .md 文件到底怎麼變成 AI 的行為？）
- 畫一條線：磁盤上的 .md 文件 → frontmatter 解析 → Command 對象 → 系統提示詞注入
- 產出：Skill 加載流程草圖

**Day 10-11：寫一個組合 Skill**
- 設計一個工作流：2-3 個步驟，每步一個 Skill
- 關鍵：Skill A 的輸出如何變成 Skill B 的輸入
- 產出：一個 Skill 組合 + 使用說明

**Day 12-13：寫一個複雜 Skill**
- 使用 `allowedTools` 限制工具範圍
- 使用 `model` 指定模型
- 使用 frontmatter 高級欄位
- 產出：一個"專業級" Skill

**Day 14：回顧日**
- 回顧你的 5 個 Skill
- 用 Day8-9 的源碼知識重新審視設計
- 改進早期 Skill
- 產出：Skill Pack v1.0，發布到 GitHub

---

## Phase 2 — 成為 Hook 開發者（第15-28天）

> 項目：為你的 Skill Pack 添加 Hook 層（3個Hook）
> 目標：理解 CC 的事件系統，能攔截和修改行為
> 驗收：Hook 在真實使用中觸發，無誤報

### Week 3 — Hook 入門（第15-21天）

**Day 15-16：觀察 Hook**
- 材料：CC 源碼官方 Hook 範例（在官方 repo `examples/hooks/` 中）
- 任務：運行 3 個官方範例 Hook，觀察它們何時觸發
- 產出：一個 Hook 事件日誌（哪個 Hook 在什麼時候觸發了）

**Day 17-18：寫第一個 Hook**
- 選一個簡單事件（如 PostToolUse）
- 寫一個 20 行 Hook：記錄特定工具的使用
- 產出：第一個 Hook

**Day 19-20：寫第二個 Hook**
- 選 PreToolUse — 在工具執行前攔截
- 做一件事：檢查 Bash 命令是否安全
- 產出：安全檢查 Hook

**Day 21：回顧日**
- 對比你的 Hook 和官方範例
- 改進

### Week 4 — Hook 深化（第22-28天）

**Day 22-23：Hook 的內部原理**
- 材料：CC 源碼 `src/hooks/` 核心文件
- 理解：Hook 註冊 → 觸發 → 執行 → 返回 的完整鏈路
- 產出：Hook 生命週期圖

**Day 24-25：Skill + Hook 整合**
- 讓 Hook 觸發 Skill，或 Skill 註冊 Hook
- 產出：一個 Skill+Hook 組合

**Day 26-27：寫一個複雜 Hook**
- 使用 Hook 修改工具輸入/輸出
- 產出：一個轉換型 Hook

**Day 28：回顧日**
- 回顧所有 Hook
- 改進後發布 Hook Pack v1.0

---

## Phase 3 — 理解 CC 架構（第29-42天）

> 項目：畫出 CC 完整架構圖（6張，逐步完成）
> 目標：能解釋 CC 任何一個子系統的設計
> 驗收：架構圖被至少一個外部讀者理解

### Week 5 — 核心循環（第29-35天）

**Day 29-31：Agent 循環**
- 材料：CC 源碼 `QueryEngine.ts` + `query.ts`
- 帶著 Phase 1-2 的實踐經驗讀，關注："我寫的 Skill/Hook 在這個循環的哪一步被觸發？"
- 產出：Agent 循環架構圖 v2

**Day 32-33：Tool 系統**
- 材料：`Tool.ts` + `tools.ts`
- 關鍵問題：如果我要給 CC 加一個新工具，要走哪些步驟？
- 產出：Tool 註冊→裝配→執行 流程圖

**Day 34-35：回顧 + 深化**
- 用架構知識回顧你的 Skill 和 Hook
- 改進

### Week 6 — 擴展與控制層（第36-42天）

**Day 36-37：Plugin 架構**
- 材料：`plugins/` + `types/plugin.ts`
- 產出：Plugin 生命週期圖

**Day 38-39：上下文工程**
- 材料：`context/`
- 產出：上下文裝配+壓縮流程圖

**Day 40-41：權限系統**
- 材料：`permissions/`
- 產出：7層防禦架構圖

**Day 42：回顧日**
- 6 張架構圖完整審查
- 發布 CC 架構圖集 v1.0

---

## Phase 4 — 構建平台（第43-56天）

> 項目：構建你的 CC 擴展平台 v1.0
> 目標：別人能安裝使用
> 驗收：至少 1 個外部用戶成功安裝並使用

### Week 7 — Plugin 開發（第43-49天）

**Day 43-45：Plugin 設計**
- 基於你的 Skill Pack + Hook Pack
- 設計一個完整 Plugin：包含 skills + hooks + 文檔

**Day 46-49：Plugin 實現 + 測試**
- 寫 manifest、打包、本地測試
- 產出：第一個 Plugin

### Week 8 — 平台發布（第50-56天）

**Day 50-52：MCP Server**
- 為你的平台添加一個 MCP Server（1-2個外部工具）
- 產出：MCP Server

**Day 53-54：平台整合**
- Skill Pack + Hook Pack + Plugin + MCP = 平台
- 統一入口、文檔、安裝指南

**Day 55-56：發布 + 回顧**
- GitHub 公開發布
- 完整回顧 8 週所學
- 產出：CC 專家學習總結

---

## 總時間線

```
Phase 1 — Skill 開發     14天    5 Skills + 理解注入機制
Phase 2 — Hook 開發      14天    3 Hooks + Skill/Hook 整合
Phase 3 — CC 架構        14天    6張架構圖 + 深層理解
Phase 4 — 平台構建        14天    Plugin + MCP + 平台發布

總計：56天 ≈ 11週 ≈ 2.5個月 @ 1h/天
每7天1天回顧/緩衝（已內建）
```

## 每日模板

```
30min — 學    讀指定材料，記錄關鍵發現
25min — 做    動手構建當天產出
 5min — 記    一句話：今天學到最重要的東西是什麼？
```

## 與 v1 的關鍵差異

| 維度 | v1 | v2 |
|------|-----|-----|
| 總時長 | 30天 | 56天（更真實） |
| 起步 | 立刻寫 | 先大量觀察 |
| 源碼時機 | Day3 | Day8（先寫3個Skill再讀） |
| 回顧 | 無 | 每7天 + 每階段末 |
| 反饋循環 | 無 | 每階段回頭改進早期作品 |
| 項目 | 碎片練習 | 一個貫穿項目：個人Skill Pack |
| MCP | 2天 | 3天+，Phase 4獨立 |
| 緩衝 | 0 | 每7天1天 |
| 驗收 | 口頭 | 能用 + 能改 + 能發布 |
