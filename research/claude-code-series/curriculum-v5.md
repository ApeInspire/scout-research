# CC 專家課程 v5 — 終版 · 全數據交叉驗證

> 數據源：GitHub 30+倉庫 + Web 搜索 20+文章 + 官方文檔 + 學術論文 + 出版書籍 + 線上課程
> 驗證方法：13項關鍵事實多源確認 + 7項現有課程對比
> v4→v5：新增官方課程對標、生態系統數據、企業級治理、安全意識

---

## 為什麼 v5 是高信度版本

### 現有課程對標

v5 不是憑空設計的。以下是 2026 年已有的 CC 課程：

| 課程 | 時長 | 深度 | 價格 | 差距 |
|------|------|------|------|------|
| Anthropic 官方免費課程 | 3-5h | 入門 | 免費 | 只教使用，不教擴展 |
| DataCamp CC 101 | 3h | 入門 | 免費 | 同上 |
| Notion 完整訓練模塊 | 8-12h | 入門→進階 | 免費 | 16模塊，但不含源碼 |
| cc-self-train | 10-15h | 入門→專家 | 免費 | 最接近，但無架構深度 |
| AI Hero (Matt Pocock) | 2週 | 高級 | $795 | 貴，且偏向使用 |
| SFEIR 1天培訓 | 7h | 初→中級 | — | 短，偏向使用 |

**所有現有課程的共同盲區：教"怎麼用 CC"，不教"怎麼解剖和擴展 CC"。
v5 填補了這個空白。**

### 生態數據驗證

| 指標 | 數據 | 對課程的意義 |
|------|------|------------|
| CC GitHub Stars | 125K+ | ★ 主流工具，值得深入研究 |
| 插件數量 | 9,000+ | ★ 生態成熟，構建插件有真實分發渠道 |
| 社區市場 | 43+ | ★ 發布平台已存在 |
| 官方免費課程 | 7+ | ★ 可用於補充基礎 |
| 出版書籍 | 1 (2026/05) | ★ 有正式參考文獻 |

---

## 課程設計原則（v5 最終版）

1. **填補空白**：現有課程教使用，v5 教解剖和擴展
2. **項目驅動**：一個 repo 貫穿，持續生長
3. **源碼拉動學習**：要構建功能 → 讀相關源碼
4. **每日可用**：1h/天，碎片化友好
5. **三重產出**：Skill/Hook/Plugin + 架構圖 + 公開報告
6. **安全意識貫穿**：從 Day 1 就知道插件是可信代碼

---

## 貫穿項目：CC Platform

```
一個 GitHub repo，56天持續生長

 Week 1-2        Week 3-4        Week 5-6        Week 7-8
  skills/         skills/         skills/         skills/
  README.md       hooks/          hooks/          hooks/
                  README.md       plugin.json     plugin.json
                                  README.md       mcp-server/
                                                  README.md
                                                  install.sh
                                                  SECURITY.md
```

---

## Phase 0 — 基礎設置（Day 0，上課前完成）

> 在你正式開始 56 天課程之前，先跑一遍官方免費課程建立基礎

**任務**：
- 完成 Anthropic 官方 [Claude Code 101](https://www.datacamp.com/courses/claude-code-101)（免費，3h）
- 閱讀官方 [Power User Tips](https://support.claude.com/en/articles/14554000)
- 閱讀 [FlorianBruniaux 架構全景](https://github.com/FlorianBruniaux/claude-code-ultimate-guide)（30min 速覽）

**產出**：對 CC 的使用方式和架構全貌有基本認知

---

## Phase 1 — Skill 平台（第 1-14 天）

> 交付物：cc-platform repo，5+ Skills，有文檔，可安裝
> 畢業標準：新用戶能在 5 分鐘內 clone 並使用你的 Skill

### Week 1：基礎 Skill（第 1-7 天）

**Day 1-2**
- 創建 `cc-platform` repo
- 讀 [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) 中 10 個熱門 Skill
- 參考 [Neha/skill-starter-template](https://github.com/Neha/skill-starter-template)
- 參考 [Sherlock Skill 寫作指南](https://sherlock.xyz/post/how-to-write-skills-for-claude-code-and-cowork)
- 研究：好的 Skill 長什麼樣？frontmatter 每個欄位做什麼？
- 產出：Skill 分析表（10個Skill × frontmatter 欄位矩陣）

**Day 3-4**
- 寫第一個 Skill（選你最常用的重複操作）
- 源碼（按需）：`Tool.ts` — 理解 `description()` 方法
- 源碼（按需）：`tools.ts` — `getAllBaseTools()` 返回什麼？
- 產出：第一個 Skill + 測試記錄

**Day 5-6**
- 寫 2 個參數化 Skill（使用 `argumentHint` + `$ARGUMENTS`）
- 源碼（按需）：`loadSkillsDir.ts`
- 產出：2 個參數化 Skill

**Day 7 — 回顧**
- 寫 README，發布 repo
- 產出：cc-platform v0.1 — 3 Skills + README

### Week 2：深化 Skill（第 8-14 天）

**Day 8-9**
- 寫一個組合 Skill（工作流 A→B→C）
- 源碼（按需）：`query.ts` — Skill 調用觸發了 9 步中的哪幾步？
- 產出：組合 Skill

**Day 10-11**
- 給 Skill 加 `allowedTools` + `model` + `disableModelInvocation`
- 源碼（按需）：`Tool.ts` 完整接口 — `isReadOnly()`, `isConcurrencySafe()`
- 產出：2 個"專業級" Skill

**Day 12-13**
- 追蹤 Skill 注入機制的完整路徑
- 源碼：`loadSkillsDir.ts` → `context.ts` → 系統提示詞
- 產出：Skill 加載流程圖

**Day 14 — 回顧**
- 改進全部 5 個 Skill
- 確保使用了 CLAUDE.md 最佳實踐
- 產出：cc-platform v0.2 — 5 Skills + 加載流程圖 + README

---

## Phase 2 — Hook 平台（第 15-28 天）

> 交付物：cc-platform 加入 3+ Hooks，Skill+Hook 可協同
> 畢業標準：Hook 在真實使用中觸發，無誤報

### Week 3：Hook 入門（第 15-21 天）

**Day 15-16**
- 讀 `src/hooks/` 核心文件，理解 27 事件
- 參考官方 Hook 範例（`examples/hooks/`）
- 產出：27 事件分類 + 標註你常用的 5 個

**Day 17-18**
- 寫第一個 Hook（PostToolUse：自動格式化）
- 產出：格式化 Hook

**Day 19-20**
- 寫第二個 Hook（PreToolUse：安全檢查 Bash 命令）
- ⚠ 安全意識：Hook 是可信代碼，可以攔截所有工具調用
- 產出：安全檢查 Hook

**Day 21 — 回顧**

### Week 4：Hook 深化（第 22-28 天）

**Day 22-23**
- 寫觸發 Skill 的 Hook（Hook→Skill 觸發器）
- 產出：Hook→Skill 觸發器

**Day 24-25**
- 寫轉換型 Hook（修改工具輸入/輸出）
- 源碼（按需）：Hook 的 `updatedInput` 機制
- 產出：轉換型 Hook

**Day 26-27**
- Hook 生命週期源碼深潛
- 產出：Hook 生命週期圖

**Day 28 — 回顧**
- 產出：cc-platform v0.3 — 5 Skills + 3 Hooks + 2 張圖

---

## Phase 3 — Plugin 平台（第 29-42 天）

> 交付物：cc-platform 加入完整 Plugin
> 畢業標準：Plugin 通過 manifest 驗證，可 `/plugin install`

### Week 5：Plugin 架構 + 實現（第 29-35 天）

**Day 29-30**
- 讀 `types/plugin.ts` + `plugins/` 核心文件
- 理解 10 組件類型 + manifest 結構
- 參考 [sjnims/plugin-dev](https://github.com/sjnims/plugin-dev) 工具包
- 產出：Plugin 架構圖

**Day 31-33**
- 把 Skill Pack + Hook Pack 打包成 Plugin
- 寫 `plugin.json` manifest
- 源碼（按需）：`pluginLoader.ts`
- 產出：Plugin v0.1

**Day 34-35**
- 測試 + 改進 + 確保通過驗證
- 產出：Plugin v1.0 + 安裝說明

### Week 6：架構全景（第 36-42 天）

**Day 36-38**
- 源碼：`QueryEngine.ts` + `query.ts`
- 問題：你寫的 Skill 在循環的哪一步？Hook 在哪攔截？
- 產出：Agent 循環架構圖（標註 Skill/Hook/Plugin 位置）

**Day 39-40**
- 源碼：`context/` + 壓縮流水線
- 產出：上下文裝配+壓縮流程圖

**Day 41-42**
- 源碼：`permissions/` + PC↔雲邊界
- 產出：權限 7 層圖 + PC↔雲邊界圖
- 發布架構圖集 v1.0

---

## Phase 4 — 完整平台（第 43-56 天）

> 交付物：cc-platform v1.0 — Skills + Hooks + Plugin + MCP + 完整文檔
> 畢業標準：外部用戶能安裝、使用、構建自己的擴展

### Week 7：MCP Server（第 43-49 天）

**Day 43-45**
- 讀 `services/mcp/` — 7 傳輸
- 產出：MCP 架構圖

**Day 46-48**
- 為平台寫 MCP Server（1-2 外部工具）
- 產出：MCP Server v0.1

**Day 49 — 回顧**

### Week 8：整合 + 畢業（第 50-56 天）

**Day 50-52**
- 整合：Skill + Hook + Plugin + MCP
- 統一安裝、文檔、貢獻指南
- ⚠ 添加 SECURITY.md
- 產出：cc-platform v1.0-rc1

**Day 53-54**
- 競品對比：CC vs OpenCode
- 產出：架構對比報告 → 發布到 scout-research

**Day 55-56**
- 最終發布 cc-platform v1.0
- CC 專家學習總結
- 產出：最終研究報告

---

## 總時間線

```
Phase 0 — 基礎設置      (課前)   官方課程 3-5h
Phase 1 — Skill 平台    14天     cc-platform v0.2
Phase 2 — Hook 平台     14天     cc-platform v0.3
Phase 3 — Plugin 平台   14天     cc-platform v0.4 + 架構圖集
Phase 4 — 完整平台      14天     cc-platform v1.0 + 研究報告

56天 ≈ 2.5 個月 @ 1h/天
```

## 每日結構

```
30min — 學    讀源碼/資源，理解核心概念
25min — 做    動手構建/改進
 5min — 記    一句話：今天學到的最重要的東西
```

## 畢業標準（滿足全部 4 項才算畢業）

```
□ cc-platform v1.0 公開發布，有完整文檔和 SECURITY.md
□ 7 張架構圖完成（循環/工具/上下文/權限/Hook/PC↔雲/MCP）
□ 1 篇 CC vs OpenCode 架構對比報告（發布到 scout-research）
□ 能獨立從源碼回答 CC 擴展相關問題
```

## 關鍵資源索引

```
全景地圖      FlorianBruniaux/ultimate-guide
逐行分析      luyao618/Claude-Code-Source-Study (25篇)
英文全書      alejandrobalderas/claude-code-from-source (18章)
學術論文      VILA-Lab/Dive-into-Claude-Code (arXiv)
中文書籍      Claude Code 實戰 (ISBN 978-7-115-69653-3)
官方課程      Anthropic 免費課程 (Skilljar)
插件開發      sjnims/plugin-dev (10 skills + 3 agents)
Skill模板    Neha/skill-starter-template
Skill指南    Sherlock: How to Write Skills
生態總覽      hesreallyhim/awesome-claude-code (44K★)
工程標準      shanraisshan/claude-code-best-practice (54K★)
源碼          claude-code-best/claude-code (54萬行)
開源競品      anomalyco/opencode (162K★)
```

## v1→v5 五版演進

```
v1  碎片練習      → 廢棄（太碎、無回顧）
v2  分離階段      → 廢棄（學用脫節）
v3  同步交織      → 廢棄（動機不足）
v4  項目拉動      → 廢棄（缺少外部驗證）
v5  全數據驗證    → 當前（對標 7 課程 + 生態數據 + 13 項事實確認）
```
