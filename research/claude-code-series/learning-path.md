# CC 學習路徑 — 優先級排序

> 目標：精通 CC 擴展開發（Hook/Skill/Plugin）
> 耗時：1h/天 ≈ 5-6週

---

## Phase 0 — 使用（先用好）

| 優先級 | 資源 | 說明 | 耗時 |
|--------|------|------|------|
| 0.1 | [shanraisshan/claude-code-best-practice](https://github.com/shanraisshan/claude-code-best-practice) 54K★ | agentic engineering 完整工作流 | 3天 |
| 0.2 | [josix/awesome-claude-md](https://github.com/josix/awesome-claude-md) 328★ | CLAUDE.md 最佳實踐合集 | 1天 |

→ 目標：理解 CC 的正確使用方式

## Phase 1 — 架構全景（先看地圖）

| 優先級 | 資源 | 說明 | 耗時 |
|--------|------|------|------|
| 1.1 | [anthropics/claude-code](https://github.com/anthropics/claude-code) 125K★ | 官方 repo，文檔/插件/Hook 範例 | 2天 |
| 1.2 | [Windy3f3f3f3f/how-claude-code-works](https://github.com/Windy3f3f3f3f/how-claude-code-works) 2.4K★ | 15篇架構深潛，最全面 | 5天 |
| 1.3 | [openedclaude/claude-reviews-claude](https://github.com/openedclaude/claude-reviews-claude) 1.4K★ | 17章，CC 審查自己源碼 | 3天 |

→ 目標：理解 CC 的架構全貌和設計決策

## Phase 2 — 源碼解剖（深入細節）

| 優先級 | 資源 | 說明 | 耗時 |
|--------|------|------|------|
| 2.1 | [claude-code-best/claude-code](https://github.com/claude-code-best/claude-code) | 54萬行源碼 v2.4.4 | — |
|  | ├─ Task.ts (126行) | 任務原子 | 1天 |
|  | ├─ Tool.ts (814行) | 工具接口 | 3天 |
|  | ├─ query.ts + QueryEngine.ts | Agent 循環 | 5天 |
|  | ├─ hooks/ + plugins/ | 擴展層 | 4天 |
|  | └─ skills/ + context/ | 技能+上下文 | 2天 |
| 2.2 | [6551Team/claude-code-design-guide](https://github.com/6551Team/claude-code-design-guide) 808★ | 46架構專題，補充參考 | 2天 |

→ 目標：理解每個模塊的源碼級設計

## Phase 3 — 極簡重現（內化）

| 優先級 | 資源 | 說明 | 耗時 |
|--------|------|------|------|
| 3.1 | [Windy3f3f3f3f/claude-code-from-scratch](https://github.com/Windy3f3f3f3f/claude-code-from-scratch) 1.2K★ | ~4000行 復現核心，11章 | 3天 |
| 3.2 | [zengyi-thinking/mini-claude](https://github.com/zengyi-thinking/mini-claude) | 2.5K行 最簡 TS 架構 | 1天 |
| 3.3 | [jiji262/build-code-agent](https://github.com/jiji262/build-code-agent) 605★ | 從零構建教程 | 2天 |

→ 目標：能從零寫出 CC 核心循環

## Phase 4 — 擴展生態（構建）

| 優先級 | 資源 | 說明 | 耗時 |
|--------|------|------|------|
| 4.1 | [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) 44K★ | Skills/Hooks/Plugins 生態總覽 | 1天 |
| 4.2 | [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) 12K★ | Skills 大全，看別人怎麼寫 | 1天 |
| 4.3 | [rohitg00/awesome-claude-code-toolkit](https://github.com/rohitg00/awesome-claude-code-toolkit) 1.7K★ | 綜合工具包，135 agents | 1天 |
| 4.4 | CC 官方 plugins/ + skills/bundled/ | 源碼中的官方範例 | 2天 |

→ 目標：能獨立開發 CC Skill/Hook/Plugin

## Phase 5 — 競品視角（對比）

| 優先級 | 資源 | 說明 | 耗時 |
|--------|------|------|------|
| 5.1 | [anomalyco/opencode](https://github.com/anomalyco/opencode) 162K★ | 開源 coding agent，Effect-TS 架構 | 2天 |
| 5.2 | [VILA-Lab/Dive-into-Claude-Code](https://github.com/VILA-Lab/Dive-into-Claude-Code) 1.2K★ | 學術論文級，跨系統對比 | 1天 |

→ 目標：理解 CC vs 競品的架構差異

---

## 總時間線

```
Phase 0 — 使用          4天    先用好
Phase 1 — 架構全景      10天    看地圖
Phase 2 — 源碼解剖      17天    深入細節
Phase 3 — 極簡重現       6天    內化核心
Phase 4 — 擴展生態       5天    開始構建
Phase 5 — 競品視角       3天    對比驗證

總計：45天 ≈ 9週 @ 1h/天
```

## 捷徑（如果時間緊）

```
只讀這些，跳過其餘：

  Phase 0.1 → 1.2 → 2.1(Task+Tool+query) → 3.1 → 4.2

  約 20 天即可開始構建第一個 Skill
```
