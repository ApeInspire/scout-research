# CC 專家培養課程

> 目標：成為 CC 專家 — 能架構分析、插件開發、平台構建
> 方法：螺旋上升，邊用邊學邊構建
> 節奏：每天 1h = 30min 學 + 30min 做
> 每日結構：任務 → 材料 → 產出 → 驗收

---

## Cycle 1 — 熟練用戶 → 第一個 Skill（第 1-5 天）

### Day 1：讀懂一個 Skill
- 材料：[travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) 12K★
- 任務：讀 5 個別人寫的 SKILL.md，理解 frontmatter 每個欄位
- 產出：筆記 — Skill frontmatter 完整欄位清單
- 驗收：能說出 name/description/allowedTools/model/argumentHint 各自的作用

### Day 2：寫第一個 Skill（自動化一個重複操作）
- 材料：CC 源碼 `src/skills/bundled/` + `src/skills/loadSkillsDir.ts`
- 任務：找到你 CC 使用中的一個痛點，寫一個 15 行的 SKILL.md
- 產出：第一個可用的 Skill
- 驗收：`/your-skill` 在 CC 中能調用，正確執行

### Day 3：Skill 的注入機制
- 材料：CC 源碼 `src/skills/loadSkillsDir.ts` + `src/context.ts`
- 任務：理解 Skill 的 .md 文件是怎麼變成 AI 能理解的系統提示詞的
- 產出：畫一張 Skill 加載流程圖
- 驗收：能說出 Skill 從磁盤到 Prompt 的完整路徑

### Day 4：寫一個參數化 Skill
- 材料：`argumentHint` + `$ARGUMENTS` 替換機制
- 任務：寫一個接收參數的 Skill（例如 `deploy <環境名>`）
- 產出：參數化 Skill
- 驗收：`/deploy production` 能正確替換參數

### Day 5：Skill 組合練習
- 材料：[rohitg00/awesome-claude-code-toolkit](https://github.com/rohitg00/awesome-claude-code-toolkit) 1.7K★
- 任務：寫一組 3 個互相配合的 Skills（例如：code-review → fix-issues → deploy）
- 產出：Skill 組合 + 使用文檔
- 驗收：3 個 Skill 能在一個工作流中連貫執行

---

## Cycle 2 — Hook 開發（第 6-10 天）

### Day 6：讀懂第一個 Hook
- 材料：CC 源碼 `src/hooks/` + official hooks examples
- 任務：理解 27 個 Hook 事件的類型和觸發時機
- 產出：Hook 事件分類圖（PreToolUse / PostToolUse / SessionStart 等）
- 驗收：能說出 5 個最常用的 Hook 事件

### Day 7：寫一個 PreToolUse Hook
- 材料：官方 hooks 範例
- 任務：寫一個 Hook，攔截 Bash 命令，記錄到本地文件
- 產出：第一個可用 Hook
- 驗收：每次 Bash 執行都被記錄

### Day 8：寫一個 PostToolUse Hook
- 材料：PostToolUse 事件定義
- 任務：寫一個 Hook，在文件寫入後自動格式化
- 產出：PostToolUse Hook
- 驗收：每次 Write 後自動觸發格式化

### Day 9：Hook + Skill 組合
- 材料：前幾天的產出
- 任務：Hook（攔截）+ Skill（處理）= 自動化工作流
- 產出：Hook+Skill 組合
- 驗收：一個操作觸發 Hook → Hook 調用 Skill → 完成

### Day 10：Hook 系統深潛
- 材料：CC 源碼 `src/hooks/` 完整閱讀
- 任務：理解 Hook 的權限模型、執行上下文、錯誤處理
- 產出：Hook 架構圖
- 驗收：能解釋 Hook 的完整生命週期

---

## Cycle 3 — CC 核心架構（第 11-16 天）

### Day 11：Agent 循環
- 材料：CC 源碼 `QueryEngine.ts` + `query.ts`
- 任務：讀懂 9 步流水線，畫出完整流程圖
- 產出：Agent 循環架構圖（已有初版，深化）
- 驗收：能說出每一步的輸入輸出

### Day 12：Tool 系統
- 材料：CC 源碼 `Tool.ts` + `tools.ts`
- 任務：理解 Tool 接口的 32 個方法，buildTool 工廠模式
- 產出：Tool 系統架構圖
- 驗收：能說出 buildTool 的 7 個默認不安全值

### Day 13：上下文工程
- 材料：CC 源碼 `context/` + `context.ts`
- 任務：理解 4-5 級壓縮流水線
- 產出：上下文裝配流程圖
- 驗收：能解釋 Context Collapse 為什麼是"可逆"的

### Day 14：權限系統
- 材料：CC 源碼 `permissions/` + `types/permissions.ts`
- 任務：理解 7 層縱深防禦，deny-first 原則
- 產出：權限模型圖
- 驗收：能說出每層防禦的職責

### Day 15：Plugin 架構
- 材料：CC 源碼 `plugins/` + `types/plugin.ts`
- 任務：理解 Plugin 的 10 組件類型 + 生命週期
- 產出：Plugin 架構圖
- 驗收：能說出 Plugin vs Skill vs Hook 的邊界

### Day 16：PC↔雲邊界
- 材料：CC 源碼 `services/api/` + 本地執行層
- 任務：理解哪些在本地執行、哪些走雲端 API
- 產出：PC↔雲邊界架構圖
- 驗收：能說出 3 個可以下移到本地的雲端操作

---

## Cycle 4 — 從分析到構建（第 17-24 天）

### Day 17-18：寫第一個 Plugin
- 材料：CC 官方 `plugins/` 範例 + `pluginLoader.ts`
- 任務：寫一個完整 Plugin（含 skill + hook）
- 產出：第一個 CC Plugin
- 驗收：Plugin 能通過 manifest 驗證，在 CC 中啟用

### Day 19-20：構建一個平台 Skill 集合
- 材料：[awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) 44K★
- 任務：把你的 3+ Skills 標準化，打包成一個平台倉庫
- 產出：GitHub repo — 你的第一個 CC 技能集合
- 驗收：別人能 `git clone` + 放入 skills 目錄直接使用

### Day 21-22：MCP Server 開發
- 材料：CC 源碼 `services/mcp/` + MCP 協議文檔
- 任務：寫一個極簡 MCP Server，提供 1 個外部工具
- 產出：第一個 MCP Server
- 驗收：CC 能連接該 MCP Server 並調用工具

### Day 23-24：整合 — 平台雛形
- 任務：Skills + Hooks + Plugin + MCP = 一個完整的 CC 擴展平台
- 產出：GitHub repo — 你的 CC 擴展平台 v0.1
- 驗收：別人安裝後能獲得一套增強的 CC 使用體驗

---

## Cycle 5 — 專家級深化（第 25-30 天）

### Day 25-26：競品對比
- 材料：`anomalyco/opencode` 162K★ + CC 源碼
- 任務：對比 CC vs OpenCode 的核心架構差異
- 產出：對比分析報告（發布到 scout-research）
- 驗收：能說出 CC 的 3 個架構優勢和 OpenCode 的 2 個

### Day 27-28：設計語言總結
- 材料：全部所學
- 任務：提煉 CC 架構的 10 個核心設計模式
- 產出：CC 設計模式手冊
- 驗收：每個模式有名字、描述、源碼引用

### Day 29-30：平台發布 + 路線圖
- 任務：發布平台 v0.1 + 發布研究報告 #001 + 規劃 v0.2
- 產出：公開發布 + 研究報告
- 驗收：外部可訪問、可使用

---

## 總時間線

```
Cycle 1 — Skill 開發      5天    熟練用戶 → 第一個 Skill
Cycle 2 — Hook 開發       5天    攔截層 → 自動化
Cycle 3 — 核心架構        6天    理解 CC 內部
Cycle 4 — 從分析到構建     8天    Plugin + MCP + 平台雛形
Cycle 5 — 專家級          6天    對比 + 設計模式 + 發布

總計：30天 ≈ 6週 @ 1h/天
```

## 每日結構

```
30min — 學    讀指定材料，理解核心概念
25min — 做    完成當天產出
 5min — 記    記錄筆記 + 提交
```

## 驗收標準

```
Cycle 1 完成：5+ Skills 可用
Cycle 2 完成：3+ Hooks 可用
Cycle 3 完成：6 張架構圖
Cycle 4 完成：1 Plugin + 1 MCP Server + 平台倉庫
Cycle 5 完成：1 研究報告 + 1 設計模式手冊 + 平台公開發布
```
