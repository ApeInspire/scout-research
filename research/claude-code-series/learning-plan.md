# CC 學習計劃 · 44天 · 5階段

> 目標：CC 專家 — 源碼級理解 + 平台構建能力
> 方法：螺旋深入，邊做邊學，架構+實戰同步
> 節奏：1h/天，碎片化友好

---

## 路線圖總覽

```
Phase 1  認知地圖       Day 1-3      看地圖，建心智模型
Phase 2  實戰構建       Day 4-20     cc-self-train 10模塊，邊做邊學
Phase 3  Agent工程      Day 21-28    設計模式+方法論+新功能
Phase 4  源碼掌握       Day 29-36    帶著問題讀源碼
Phase 5  平台發布       Day 37-44    整合打包公開發布
```

---

## Phase 1 — 認知地圖（Day 1-3）

> 目標：建立 CC 完整心智模型
> 方法：速覽，不全做。只看"有什麼"。

| 天 | 任務 | 資源 | 重點 |
|----|------|------|------|
| 1 | CC 全貌速覽 | [luongnv89/claude-howto](https://github.com/luongnv89/claude-howto) | 模塊1-5：安裝、基本工作流、CLAUDE.md、核心工具 |
| 2 | CC 全貌速覽 | [luongnv89/claude-howto](https://github.com/luongnv89/claude-howto) | 模塊6-10：Skills、Hooks、MCP、Subagents、Plugin |
| 3 | Agent工具設計哲學 | [Seeing Like an Agent](https://claude.com/blog/seeing-like-an-agent) | 漸進式披露、Tool設計原則、為什麼只有~20個工具 |

**產出**：一張 CC 知識地圖（手繪或 Markdown）

---

## Phase 2 — 實戰構建（Day 4-20）

> 目標：邊做邊學，每個模塊有產出
> 主框架：[cc-self-train](https://github.com/zainnab-sparq/cc-self-train)

| 天 | 模塊 | 任務 | 架構參考（按需） | 產出 |
|----|------|------|-----------------|------|
| 4-5 | M1: Setup | 優化 CLAUDE.md | [Power User Tips](https://support.claude.com/en/articles/14554000) | 優化後的 CLAUDE.md |
| 6-7 | M2: Plan/Build | Explore→Plan→Code→Commit | — | 第一個完整工作流 |
| 8-9 | M3: Memory/Context | 上下文管理 | [FlorianBruniaux Guide](https://github.com/FlorianBruniaux/claude-code-ultimate-guide) 壓縮章節 | 上下文管理筆記 |
| 10-11 | M4: Skills | 寫 3 個 Skill | [luyao618 Tool.ts](https://github.com/luyao618/Claude-Code-Source-Study) | 3 個 Skill |
| 12-13 | M5: Hooks | 寫 2 個 Hook | [Build Your Own Agent](https://github.com/VILA-Lab/Dive-into-Claude-Code/blob/main/docs/build-your-own-agent.md) 安全章節 | 2 個 Hook |
| 14-15 | M6: MCP | MCP Server | — | MCP Server 雛形 |
| 16-17 | M7: Guard Rails | 安全規則 | FlorianBruniaux 安全威脅數據庫 | 安全配置 |
| 18 | M8: Subagents | 子Agent | [Agent Teams 詳解](https://addyosmani.com/blog/claude-code-agent-teams/) | 子Agent 配置 |
| 19 | M9: Tasks/TDD | 任務管理 | — | 任務模板 |
| 20 | M10: Plugin | 打包 Skill+Hook | [everything-claude-code-zh](https://github.com/xu-xiang/everything-claude-code-zh) 配置參考 | Plugin 雛形 |

**產出**：cc-platform v0.5（Skills + Hooks + Plugin 雛形 + MCP Server 雛形）

---

## Phase 3 — Agent 工程（Day 21-28）

> 目標：補齊 Agent 工程方法論
> 方法：精讀設計模式 + 研究實戰配置

| 天 | 任務 | 資源 | 產出 |
|----|------|------|------|
| 21-22 | Agent 設計模式 | [Agentic Harness Patterns](https://github.com/keli-wen/agentic-harness-patterns-skill) | Agent 設計模式筆記 |
| 23-24 | Agent 方法論 | [my-claude-devteam](https://github.com/NYCU-Chung/my-claude-devteam) P7/P9/P10 | 方法論筆記 + Agent 配置模板 |
| 25-26 | Agent Teams/Swarm | [Code w/ Claude SF 2026](https://claude.com/blog/code-w-claude-sf-2026-sf) + [Swarm中文](https://developer.aliyun.com/article/1711162) | Agent Teams 架構圖 |
| 27-28 | 回顧 + 改進 | 用 Phase 3 所學改進 Phase 2 的 Skill/Hook | 改進後的 Skill Pack + Hook Pack |

**產出**：Agent 工程筆記 + 改進後的 cc-platform v0.6

---

## Phase 4 — 源碼掌握（Day 29-36）

> 目標：帶著實戰問題，源碼級理解 CC
> 方法：按問題查源碼，不全讀

| 天 | 任務 | 資源 | 產出 |
|----|------|------|------|
| 29-30 | Agent 循環 | [luyao618 QueryEngine+query](https://github.com/luyao618/Claude-Code-Source-Study) + [VILA-Lab](https://github.com/VILA-Lab/Dive-into-Claude-Code) 設計哲學 | Agent 循環架構圖 |
| 31-32 | Tool 系統 + 上下文 | [luyao618 Tool.ts+Context](https://github.com/luyao618/Claude-Code-Source-Study) + [FlorianBruniaux](https://github.com/FlorianBruniaux/claude-code-ultimate-guide) | Tool 系統圖 + 上下文裝配圖 |
| 33-34 | Hook + 權限 + Plugin | [luyao618 Hook+Plugin](https://github.com/luyao618/Claude-Code-Source-Study) + [yaniv-golan](https://github.com/yaniv-golan/claude-code-internals)（按需） | Hook生命週期圖 + 權限7層圖 |
| 35-36 | PC↔雲邊界 + MCP | 源碼 `services/api/` + `services/mcp/` | PC↔雲邊界圖 + MCP架構圖 |

**產出**：6 張架構圖（循環/工具/上下文/權限/Hook/PC↔雲+MCP）

---

## Phase 5 — 平台發布（Day 37-44）

> 目標：整合全部產出，公開發布
> 方法：打包、文檔、發布

| 天 | 任務 | 參考 |
|----|------|------|
| 37-38 | 平台整合 | [everything-claude-code-zh](https://github.com/xu-xiang/everything-claude-code-zh) 配置結構 |
| 39-40 | 文檔 + 安裝腳本 | [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) 生態參考 |
| 41-42 | 競品對比 | [OpenCode](https://github.com/anomalyco/opencode) 架構對比 |
| 43-44 | 最終發布 + 學習總結 | cc-platform v1.0 + 研究報告 |

**產出**：cc-platform v1.0（公開發布）+ CC vs OpenCode 架構對比報告

---

## 每日模板

```
30min — 學    讀當天指定資源
25min — 做    完成當天任務，產出加入 cc-platform
 5min — 記    一句話：今天學到最重要的一個東西
```

## 畢業標準

```
□ cc-platform v1.0 公開發布
□ 6 張架構圖完成
□ 5+ Skills、3+ Hooks、1 Plugin、1 MCP Server
□ CC vs OpenCode 架構對比報告
□ 能獨立從 CC 源碼回答擴展相關問題
```

## 核心資源速查

| 用途 | 資源 |
|------|------|
| 認知地圖 | luongnv89/claude-howto |
| 主框架 | cc-self-train |
| 架構參考 | FlorianBruniaux Guide |
| 源碼分析 | luyao618 25篇 |
| Agent工程 | Agentic Harness Patterns |
| 方法論 | my-claude-devteam P7/P9/P10 |
| 生態查閱 | awesome-claude-code |
| 權威文檔 | code.claude.com/docs |
