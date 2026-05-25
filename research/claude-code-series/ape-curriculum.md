# Ape 定制課程 — 基於現有最佳教程

> 不是憑空設計。是研究 6 套現有教程後，針對你的背景定制。
> 每步都標註來源。

---

## 參考的 6 套教程

| 教程 | 時長 | 特點 | 適合你的部分 |
|------|------|------|------------|
| **cc-self-train** (10模塊) | 10-15h | 項目驅動，邊做邊學 | ★ 主框架 — 最接近你的風格 |
| **agentic-ai-from-claude-code** (10週) | — | 源碼級架構深潛 | ★ 架構深度 — 填補你的需求 |
| **yaniv-golan/claude-code-internals** (71課) | — | 源碼驗證，13章 | ★ 源碼參考 — 深入時查閱 |
| **Tim Warner/O'Reilly** (4h) | 4h | 結構化直播課 | 快速概覽 |
| **Notion Complete Training** (16模塊) | 8-12h | 入門→進階 | 基礎補充（已跳過） |
| **Claude Code 實戰 (書)** | — | 正式出版物 | 參考手冊 |

## 你不需要的（已砍）

```
✗ MCP 基礎概念              → 你已在用
✗ 什麼是 LLM/Token/Agent    → 你已理解
✗ 如何安裝 CC               → 你已安裝
✗ 如何寫 prompt             → 你已熟練
✗ 非工程 AI 應用             → 來自 minicoohei/ai-agent-camp（24h），全砍
```

## 你的定制路徑

### 原則
1. 主框架 = cc-self-train（項目驅動，10模塊）
2. 架構深度 = agentic-ai-from-claude-code（每個模塊對應的架構知識）
3. 源碼參考 = yaniv-golan/claude-code-internals（具體文件+行號）
4. 你的節奏 = 用痛驅動，不是按課表

### 模塊映射

```
cc-self-train          agentic-ai-from-cc        你的產出
──────────────         ─────────────────         ────────
M1: Setup/CLAUDE.md    Week1-2: Architecture     CLAUDE.md 優化
M2: Plan/Build         Week3-4: Tool System      理解循環
M3: Memory/Context     Week7-8: Context Mgmt     Skill #1-2
M4: Skills/Commands    Week3-4: Tool System      Skill #3-5
M5: Hooks              Week5-6: Orchestration    Hook #1-3
M6: MCP Servers        Week7-8: Advanced         MCP Server
M7: Guard Rails        Week1-2: Permissions      安全審計
M8: Subagents          Week5-6: Orchestration    多 Agent
M9: Tasks/TDD          Week9-10: Projects        實戰
M10: Plugins/Eval      Week7-8: Advanced         Plugin+平台
```

---

## 你的路線圖

### M1 — CLAUDE.md + CC 架構全景（第 1-5 天）

> 來源：cc-self-train M1 + agentic-ai-from-cc Week1-2

**Day 1：審計你現有的 CLAUDE.md**
- 讀 /Users/stan/Myspace/Scout/CLAUDE.md
- 對比 cc-self-train 的 CLAUDE.md 最佳實踐
- 對比 Anthropic 官方 Power User Tips 中的 CLAUDE.md 指南
- 改進你的 CLAUDE.md
- 產出：優化後的 CLAUDE.md

**Day 2-3：CC 架構全景**
- 來源：agentic-ai-from-cc Week1 + FlorianBruniaux ultimate-guide
- Agent 循環 = while loop（一句話理解）
- 雙層生成器（QueryEngine + query）
- 9 步流水線（每步一句話）
- 8 個核心工具（每個一句話）
- 產出：一張手繪 Agent 循環圖

**Day 4-5：第一個 Skill**
- 來源：cc-self-train M4
- 找到你今天用 CC 時的一個重複操作
- 寫第一個 SKILL.md
- 測試 `/your-skill`
- 產出：第一個可用 Skill + 加入 cc-platform repo

### M2 — Skill 深化（第 6-10 天）

> 來源：cc-self-train M4 + agentic-ai-from-cc Week3-4 Tool System

**Day 6-7：Tool 系統理解**
- 源碼：Tool.ts — 32個方法接口
- 理解：Skill 的 allowedTools 怎麼映射到 Tool 接口
- 產出：Tool 接口快速參考

**Day 8-9：參數化 Skill + 組合**
- 寫 2 個參數化 Skill
- 寫 1 個組合 Skill（A→B 工作流）
- 產出：3 個 Skill

**Day 10：Skill 加載機制**
- 源碼：loadSkillsDir.ts → context.ts
- 產出：Skill 加載流程圖

### M3 — Hook 系統（第 11-16 天）

> 來源：cc-self-train M5 + agentic-ai-from-cc Week5-6

**Day 11-12：Hook 架構**
- 27 事件分類
- PreToolUse vs PostToolUse
- 產出：Hook 事件圖

**Day 13-14：寫 Hook**
- PostToolUse Hook（自動格式化）
- PreToolUse Hook（安全檢查）
- 產出：2 個 Hook

**Day 15-16：Hook + Skill 整合**
- Hook 觸發 Skill
- Hook 生命週期源碼
- 產出：Hook→Skill 觸發器

### M4 — Plugin + 架構深化（第 17-24 天）

> 來源：cc-self-train M10 + agentic-ai-from-cc Week7-8

**Day 17-19：Plugin 打包**
- 把 Skill+Hook 打包成 Plugin
- 寫 manifest，測試
- 產出：Plugin v1.0

**Day 20-22：Agent 循環源碼深潛**
- QueryEngine.ts + query.ts
- 產出：Agent 循環完整架構圖

**Day 23-24：架構全景整合**
- Context/Compaction/Permissions
- 產出：3 張架構圖

### M5 — MCP + 平台發布（第 25-30 天）

> 來源：cc-self-train M6 + 你的平台目標

**Day 25-27：MCP Server**
- 為平台添加外部工具
- 產出：MCP Server

**Day 28-30：整合 + 發布**
- Skill+Hook+Plugin+MCP 整合
- cc-platform v1.0 發布
- 產出：公開發布的 CC 平台

---

## 總時間線

```
M1 — CLAUDE.md+架構     5天     優化 CLAUDE.md + 架構圖 + Skill #1
M2 — Skill 深化         5天     5 Skills + 加載流程圖
M3 — Hook 系統          6天     3 Hooks + Skill/Hook 整合
M4 — Plugin+架構深化     8天     Plugin + 6張架構圖
M5 — MCP+平台發布        6天     MCP Server + cc-platform v1.0

30天 ≈ 6週 @ 1h/天
```

## 每日格式

```
不是 30min 學 + 30min 做。
是：你遇到一個真實問題 → 我給你對應的架構知識 → 你立刻解決它。

每次你問"為什麼" → 我打開源碼 → 一起看 → 你立刻構建。
```
