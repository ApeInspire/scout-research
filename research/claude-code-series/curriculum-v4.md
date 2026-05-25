# CC 專家課程 v4 — 項目驅動螺旋版

> v3 問題：架構學習和實踐並列但動機不足。架構是"應該學"而不是"需要學"。
> v4 修正：一個貫穿項目驅動所有學習。要構建下一個功能 → 必須讀懂相關源碼。

---

## 設計原則

1. **項目拉動學習**：不是"今天該學 Tool 了"，是"今天要給 Skill 加 allowedTools，必須讀 Tool.ts"
2. **一個項目貫穿**：從 Day1 到最後一天，同一個 repo 持續生長
3. **里程碑制**：每階段有明確交付物。達標才進入下一階段
4. **彈性節奏**：每天有建設性任務，但可根據當天狀態調整深度
5. **畢業標準**：不是"讀完了"，是"能獨立從源碼回答任何 CC 相關問題 + 平台公開發布"

---

## 貫穿項目：CC Platform

```
一個 GitHub repo，從 Day1 開始構建，8週後變成一個完整的 CC 擴展平台。

 Week 1-2        Week 3-4        Week 5-6        Week 7-8
  skills/         skills/         skills/         skills/
                  hooks/          hooks/          hooks/
                                  plugin.json     plugin.json
                                                  mcp-server/
                                                  README.md
                                                  install.sh
```

---

## Phase 1 — Skill 平台（第 1-14 天）

> 交付物：一個 GitHub repo，包含 5+ 個 Skill，有文檔，可安裝
> 畢業標準：一個新用戶能 clone 並在 5 分鐘內使用你的第一個 Skill

### Week 1：基礎 Skill（第 1-7 天）

**Day 1-2**
- 任務：創建 `cc-platform` repo。讀 [awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) 中的 10 個熱門 Skill
- 研究問題：好的 Skill 長什麼樣？frontmatter 每個欄位做什麼？
- 源碼（按需）：`Tool.ts` — 理解 `description()` 方法——這就是 Skill 的 description 欄位最終到達的地方
- 產出：Skill 分析表（10個Skill × frontmatter欄位矩陣）

**Day 3-4**
- 任務：寫第一個 Skill（選你最常用的一個操作）
- 源碼（按需）：`tools.ts` — `getAllBaseTools()` 返回哪些工具？你的 `allowedTools` 要引用哪些？
- 產出：第一個 Skill + 測試記錄

**Day 5-6**
- 任務：寫 2 個參數化 Skill
- 源碼（按需）：`loadSkillsDir.ts` — 理解 `$ARGUMENTS` 替換機制
- 產出：2 個參數化 Skill

**Day 7**
- 任務：寫 README，發布 repo
- 不學新東西。回顧、改進、整理。
- 產出：cc-platform v0.1 — 3 個 Skill + README

### Week 2：深化 Skill（第 8-14 天）

**Day 8-9**
- 任務：寫一個組合 Skill（A→B→C 工作流）
- 源碼（按需）：`query.ts` 9 步流水線中 Skill 調用佔了哪幾步？
- 產出：組合 Skill

**Day 10-11**
- 任務：給 Skill 加 `allowedTools` 限制 + 用 `model` 指定模型
- 源碼（按需）：`Tool.ts` 完整接口——理解 `isReadOnly()`, `isDestructive()`, `isConcurrencySafe()` 在 Skill 語境下的意義
- 產出：2 個"專業級" Skill

**Day 12-13**
- 任務：理解 Skill 注入機制的完整路徑
- 源碼：`loadSkillsDir.ts` → `context.ts` → 系統提示詞組裝
- 畫出：磁盤上的 .md → frontmatter 解析 → Command 對象 → 系統提示詞的一條線
- 產出：Skill 加載流程圖

**Day 14**
- 回顧 + 改進全部 5 個 Skill
- 產出：cc-platform v0.2 — 5 個 Skill + 加載流程圖 + 改進的 README

---

## Phase 2 — Hook 平台（第 15-28 天）

> 交付物：cc-platform 加入 3+ Hook，Skill+Hook 可協同工作
> 畢業標準：Hook 在真實使用中觸發，無誤報，且和 Skill 有明確協作關係

### Week 3：Hook 入門（第 15-21 天）

**Day 15-16**
- 任務：讀 `src/hooks/` 核心文件，理解 27 個事件
- 研究問題：哪些事件在你的日常使用中最常觸發？
- 產出：27 事件分類圖 + 標註你最可能用的 5 個

**Day 17-18**
- 任務：寫第一個 Hook（PostToolUse — 文件寫入後自動格式化）
- 源碼（按需）：Hook 執行上下文——Hook 能訪問什麼？不能訪問什麼？
- 產出：格式化 Hook

**Day 19-20**
- 任務：寫第二個 Hook（PreToolUse — Bash 命令安全檢查）
- 源碼（按需）：`permissions/` — Hook 的 deny 如何與 7 層權限協作？
- 產出：安全檢查 Hook

**Day 21**
- 回顧，改進
- 產出：2 個可用的 Hook

### Week 4：Hook 深化（第 22-28 天）

**Day 22-23**
- 任務：寫一個觸發 Skill 的 Hook
- 關鍵設計：Hook 攔截事件 → 觸發 Skill → Skill 處理 → 返回結果
- 產出：Hook→Skill 觸發器

**Day 24-25**
- 任務：寫一個轉換型 Hook（修改工具輸入或輸出）
- 源碼（按需）：Hook 的 `updatedInput` 機制
- 產出：轉換型 Hook

**Day 26-27**
- 任務：Hook 生命週期源碼深潛
- 源碼：註冊 → 觸發條件匹配 → 執行 → 返回 → 錯誤處理 的完整鏈路
- 產出：Hook 生命週期圖

**Day 28**
- 回顧 + 改進全部 Hook
- 確保每個 Hook 和至少一個 Skill 有協作關係
- 產出：cc-platform v0.3 — 5 Skills + 3 Hooks + 2 張架構圖

---

## Phase 3 — Plugin 平台（第 29-42 天）

> 交付物：cc-platform 加入一個完整 Plugin（打包 Skill+Hook）
> 畢業標準：Plugin 通過 manifest 驗證，可在 CC 中 `/plugin install` 安裝

### Week 5：Plugin 架構 + 實現（第 29-35 天）

**Day 29-30**
- 任務：讀 `types/plugin.ts` + `plugins/` 核心文件
- 理解：Plugin 的 10 組件類型 + manifest 結構
- 產出：Plugin 架構圖

**Day 31-33**
- 任務：把你的 Skill Pack + Hook Pack 打包成一個 Plugin
- 寫 `plugin.json` manifest，組織目錄結構
- 源碼（按需）：`pluginLoader.ts` — Plugin 是怎麼被發現和加載的？
- 產出：Plugin v0.1

**Day 34-35**
- 任務：本地測試 Plugin、改進、確保通過驗證
- 產出：Plugin v1.0 + 安裝說明

### Week 6：架構全景（第 36-42 天）

> 這時你已有 Skill+Hook+Plugin 的完整實踐經驗
> 現在回頭看 CC 核心架構，每個設計決策都有了意義

**Day 36-38**
- 源碼：`QueryEngine.ts` + `query.ts`
- 帶著問題讀：你寫的 Skill 在循環的哪一步被觸發？Hook 在哪一步攔截？
- 產出：Agent 循環完整架構圖（標註 Skill/Hook/Plugin 的位置）

**Day 39-40**
- 源碼：`context/` + 壓縮流水線
- 問題：壓縮對你的 Skill 提示詞有什麼影響？
- 產出：上下文裝配+壓縮流程圖

**Day 41-42**
- 源碼：`permissions/` + PC↔雲邊界
- 產出：權限7層圖 + PC↔雲邊界圖
- 回顧：6 張架構圖完成。發布架構圖集。

---

## Phase 4 — 完整平台（第 43-56 天）

> 交付物：cc-platform v1.0 — Skills + Hooks + Plugin + MCP Server + 完整文檔
> 畢業標準：外部用戶能安裝、使用、並基於你的平台構建自己的擴展

### Week 7：MCP Server（第 43-49 天）

**Day 43-45**
- 任務：讀 `services/mcp/` — MCP 協議和 7 種傳輸
- 理解：MCP Server 如何變成 CC 可以調用的工具
- 產出：MCP 架構圖

**Day 46-48**
- 任務：為你的平台寫一個 MCP Server（1-2 個外部工具）
- 產出：MCP Server v0.1

**Day 49**
- 回顧，測試，改進

### Week 8：整合 + 畢業（第 50-56 天）

**Day 50-52**
- 任務：整合一切 — Skill + Hook + Plugin + MCP
- 統一安裝腳本、使用文檔、貢獻指南
- 產出：cc-platform v1.0-rc1

**Day 53-54**
- 任務：競品對比 — 讀 OpenCode 架構，對比 CC
- 用 8 週的知識形成自己的判斷
- 產出：CC vs OpenCode 架構對比（發布到 scout-research）

**Day 55-56**
- 最終發布 cc-platform v1.0
- CC 專家學習總結：我學到了什麼？我構建了什麼？下一步是什麼？

---

## 總時間線

```
Phase 1 — Skill 平台     14天    cc-platform v0.2
Phase 2 — Hook 平台      14天    cc-platform v0.3
Phase 3 — Plugin 平台    14天    cc-platform v0.4 + 架構圖集
Phase 4 — 完整平台        14天    cc-platform v1.0 + 研究報告

56天 ≈ 2.5個月 @ 1h/天
```

## 每日結構（彈性）

```
好的日子（有深度）：
  60min 連續 — 源碼深潛 + 對應構建

碎片的日子：
  15min × N — 讀一段源碼 → 寫一段代碼 → 測試
```

## v4 vs v3 — 關鍵差異

```
v3                               v4
─────────────────────────        ─────────────────────────
架構和實踐"並列"安排             項目"拉動"源碼學習
"今天該學Tool了"                  "今天要讓Skill限制工具→必須讀Tool"
每天任務固定                      里程碑驅動，節奏彈性
平台在Phase4才出現                平台從Day1創建，持續生長
無畢業標準                        明確畢業標準：能用+能改+能發布

一個 repo，從 Day1 到最後一天，持續生長。
每行源碼都是為了解決當前的構建問題而讀。
```

## 四個版本演進

```
v1  碎片練習      → 太碎、無回顧
v2  分離階段      → 架構和實踐脫節
v3  同步交織      → 動機不足、"應該學"不是"需要學"
v4  項目拉動      → 一個 repo、一個平台、真實驅動力
```
