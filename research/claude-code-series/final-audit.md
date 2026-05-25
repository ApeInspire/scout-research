# CC 資源終版 — 全量審計 · 排名 · 路線圖

> 數據截止：2026-05-25
> 總資源：35 個
> 審計輪次：4 輪搜索 + 3 輪交叉驗證
> 覆蓋維度：使用 · 架構 · 源碼 · Agent工程 · 擴展開發 · 生態

---

## 一、全量資源排名

### 評分標準

| 維度 | 權重 | 說明 |
|------|------|------|
| 目標匹配 | 10 | 對平台構建+源碼理解+Agent工程化的直接幫助 |
| 深度質量 | 10 | 資訊密度、準確性、時效性 |
| 學習風格 | 10 | 架構先行+實戰驅動+Fowler式解剖的匹配度 |
| 時間效率 | 10 | 每小時學到有用知識的量 |
| 不可替代 | 10 | 其他資源無法覆蓋的獨特價值 |

### A+ 級 — 首選（≥45分）

| # | 資源 | 鏈接 | 得分 | 目標 | 質量 | 風格 | 效率 | 獨特 | 判決理由 |
|---|------|------|------|------|------|------|------|------|----------|
| 1 | **cc-self-train** | [GitHub](https://github.com/zainnab-sparq/cc-self-train) | **48** | 10 | 9 | 10 | 10 | 9 | 唯一項目驅動實戰課程。10模塊邊做邊學。v2.30 May2026。和你的學習風格完全一致 |
| 2 | **luongnv89/claude-howto** | [GitHub](https://github.com/luongnv89/claude-howto) | **46** | 9 | 10 | 9 | 10 | 8 | 30K★可視化教程，含練習題和模板。最快建立完整認知地圖 |
| 3 | **Agentic Harness Patterns** | [GitHub](https://github.com/keli-wen/agentic-harness-patterns-skill) | **46** | 10 | 9 | 9 | 9 | 9 | 6設計模式章節+11深潛參考，提煉自CC源碼，中英雙語，跨平台。**Agent工程化核心** |
| 4 | **FlorianBruniaux Guide** | [GitHub](https://github.com/FlorianBruniaux/claude-code-ultimate-guide) | **45** | 9 | 10 | 9 | 8 | 9 | 最完整單頁架構參考。41張Mermaid圖。24 CVE數據庫。271題測驗。三級置信度標註 |
| 5 | **Seeing Like an Agent** | [claude.com](https://claude.com/blog/seeing-like-an-agent) | **45** | 10 | 10 | 8 | 9 | 8 | Anthropic官方：如何為Agent設計工具。漸進式披露哲學。Tool設計的藝術 |

### A 級 — 必學（40-44分）

| # | 資源 | 鏈接 | 得分 | 判決理由 |
|---|------|------|------|----------|
| 6 | **luyao618 源碼分析** | [GitHub](https://github.com/luyao618/Claude-Code-Source-Study) | **44** | 25篇中文逐文件逐函數源碼分析。縮短讀源碼時間10倍。唯一 |
| 7 | **官方文檔** | [code.claude.com](https://code.claude.com/docs) | **43** | Agent SDK/Agent Loop/Tools/Hooks/MCP。權威性無可替代 |
| 8 | **everything-claude-code-zh** | [GitHub](https://github.com/xu-xiang/everything-claude-code-zh) | **41** | 80+中文配置，黑客松冠軍實戰。13 Agents+56 Skills+32 Commands |

### B+ 級 — 強烈推薦（35-39分）

| # | 資源 | 鏈接 | 得分 | 判決理由 |
|---|------|------|------|----------|
| 9 | **VILA-Lab 學術論文** | [GitHub](https://github.com/VILA-Lab/Dive-into-Claude-Code) | **38** | arXiv:2604.14228。5 Values→13 Principles。學術級系統分析 |
| 10 | **Code w/ Claude SF 2026** | [claude.com](https://claude.com/blog/code-w-claude-sf-2026-sf) | **38** | Dreaming+Multiagent+Outcomes+Webhooks。2026年5月最新 |
| 11 | **my-claude-devteam** | [GitHub](https://github.com/NYCU-Chung/my-claude-devteam) | **37** | P7/P9/P10方法論。12Agent+15Hook。工程團隊即開即用 |
| 12 | **CC Agent Teams 詳解** | [addyosmani](https://addyosmani.com/blog/claude-code-agent-teams/) | **36** | Agent Teams架構+郵箱系統+3-5-6法則 |
| 13 | **Build Your Own Agent** | [VILA-Lab](https://github.com/VILA-Lab/Dive-into-Claude-Code/blob/main/docs/build-your-own-agent.md) | **35** | 6個關鍵Agent設計決策。每個Agent構建者必讀 |

### B 級 — 推薦（30-34分）

| # | 資源 | 鏈接 | 得分 | 判決理由 |
|---|------|------|------|----------|
| 14 | **alejandrobalderas 全書** | [GitHub](https://github.com/alejandrobalderas/claude-code-from-source) | **34** | 18章400頁。10設計模式。和luyao618有重疊，選讀 |
| 15 | **agentic-ai-from-cc** | [GitHub](https://github.com/ahmedk20/agentic-ai-from-claude-code) | **34** | 10週路徑。參考結構，不全跟 |
| 16 | **CC Swarm 蜂群 (中文)** | [阿里雲](https://developer.aliyun.com/article/1711162) | **34** | Agent Swarm架構中文詳解 |
| 17 | **最佳實踐** | [GitHub](https://github.com/shanraisshan/claude-code-best-practice) | **33** | 54K★，83 tips。補充官方文檔 |
| 18 | **awesome-claude-code** | [GitHub](https://github.com/hesreallyhim/awesome-claude-code) | **33** | 44K★生態總索引。查閱工具 |
| 19 | **yaniv-golan 內部架構** | [GitHub](https://github.com/yaniv-golan/claude-code-internals) | **33** | 71課源碼級。精確查詢用 |
| 20 | **50萬行源碼架構** | [CSDN](https://grapecity.csdn.net/6a0e6fcc662f9a54cb7606ad.html) | **33** | 7恢復+10終止+流式並發 |
| 21 | **CC實戰（書）** | ISBN 978-7-115-69653-3 | **32** | 唯一正式出版物。結構參考 |
| 22 | **Power User Tips (官方)** | [support.claude.com](https://support.claude.com/en/articles/14554000) | **31** | CLAUDE.md權威指南+核心工作流 |

### C 級 — 可選（20-29分）

| # | 資源 | 鏈接 | 得分 | 判決理由 |
|---|------|------|------|----------|
| 23 | 實踐 Wiki | [GitHub](https://github.com/MuhammadUsmanGM/claude-code-best-practices) | 28 | CLAUDE.md模板，對你太基礎 |
| 24 | Tim Warner O'Reilly | [GitHub](https://github.com/timothywarner-org/claude-code) | 27 | 4h入門課，你已過這階段 |
| 25 | 阿里雲 Plugin 拆解 | [阿里雲](https://developer.aliyun.com/article/1736450) | 26 | 已有多資源覆蓋 |
| 26 | 官方博客 (企業級) | [claude.com](https://claude.com/blog/how-claude-code-works-in-large-codebases) | 26 | 和Power User Tips重疊 |
| 27 | 掘金 Plugin 連載 | [掘金](https://juejin.cn/post/7638529212292038707) | 25 | 按需查閱 |

### D 級 — 跳過（<20分）

| # | 資源 | 得分 | 理由 |
|---|------|------|------|
| 28 | minicoohei/ai-agent-camp | 18 | 面向非工程師，無關 |
| 29 | DataCamp CC 101 | 15 | 3h入門，你已是重度用戶 |
| 30 | Notion Complete Training | 14 | 和cc-self-train重疊 |
| 31 | Scrimba/Coursera/Udemy | 12 | 入門級，付費，不需要 |

### 源碼

| # | 資源 | 鏈接 | 用途 |
|---|------|------|------|
| 32 | CC 逆向源碼 | [GitHub](https://github.com/claude-code-best/claude-code) | 54萬行 v2.4.4，可構建 |
| 33 | OpenCode 開源競品 | [GitHub](https://github.com/anomalyco/opencode) | 162K★，架構對比 |

### 官方

| # | 資源 | 鏈接 |
|---|------|------|
| 34 | 官方 repo | [GitHub](https://github.com/anthropics/claude-code) |
| 35 | BAAI 中文論文解讀 | [hub.baai.ac.cn](https://hub.baai.ac.cn/view/54569) |

---

## 二、查漏補缺審計

### 之前缺失、現已補齊

| 缺口 | 補齊資源 | 重要性 |
|------|---------|--------|
| Agent工程化方法論 | Agentic Harness Patterns (#3) | ★★★ |
| Agent工具設計哲學 | Seeing Like an Agent (#5) | ★★★ |
| Agent Teams/Swarm架構 | #10, #12, #16 | ★★☆ |
| P7/P9/P10工程方法 | my-claude-devteam (#11) | ★★☆ |
| Agent設計決策框架 | Build Your Own Agent (#13) | ★★☆ |
| 2026年5月新功能 | Code w/ Claude SF 2026 (#10) | ★★☆ |
| 中文Agent工程資源 | everything-claude-code-zh (#8) | ★★☆ |

### 覆蓋度確認

```
使用層    ████████  5個資源  官方Tips+最佳實踐+實戰課程
架構層    ████████  7個資源  UltimateGuide+學術論文+全書+源碼分析
源碼層    ████████  4個資源  逆向源碼+25篇分析+71課+內部架構
Agent層   ████████  6個資源  HarnessPatterns+AgentTeams+P7/P9/P10+設計決策
擴展層    ████████  5個資源  Plugin拆解+Skill指南+Hook開發+awesome生態
生態層    ████████  4個資源  44K總索引+54K最佳實踐+競品+配置合集
官方層    ████████  4個資源  Docs+Blog+Repo+PowerUserTips

全部7個維度完整覆蓋 ✓
```

---

## 三、最終學習路線圖

### Phase 1 — 認知地圖（Day 1-3）

```
#1  luongnv89/claude-howto         速覽全貌，建立心智模型
    重點模塊：CLAUDE.md、核心工作流、8個工具、擴展機制概覽
    方法：速覽，不全做。只建立"有什麼"的認知。

#2  Seeing Like an Agent (官方)    理解Agent工具設計哲學
    重點：漸進式披露、Tool設計原則
    方法：精讀。20分鐘。

產出：CC知識地圖（一張圖）
```

### Phase 2 — 實戰構建（Day 4-20）

```
#3  cc-self-train                   主框架。10模塊邊做邊學。
    M1-2 → CLAUDE.md+Plan/Build
    M3   → Memory+Context（→ 翻 FlorianBruniaux 架構圖）
    M4   → Skills+Commands（→ 翻 everything-claude-code-zh 配置）
    M5   → Hooks（→ 讀 #13 BuildYourOwnAgent 安全設計決策）
    M6   → MCP Servers
    M7   → Guard Rails（→ 翻 FlorianBruniaux 安全威脅數據庫）
    M8   → Subagents（→ 翻 #12 AgentTeams詳解）
    M9   → Tasks+TDD
    M10  → Plugins+Evaluation

每完成一個模塊 → 產出對應的 Skill/Hook/Plugin → 加入 cc-platform repo

產出：cc-platform v0.5（Skills+Hooks+Plugin雛形）
```

### Phase 3 — Agent工程深潛（Day 21-28）

```
#4  Agentic Harness Patterns        6設計模式+11深潛參考
    重點：AsyncGenerator循環、Fork Agent、Speculative Execution
    方法：精讀。對比你實戰中遇到的問題。

#5  Code w/ Claude SF 2026          Dreaming+Multiagent+Outcomes
    重點：2026年5月新發布的功能
    方法：速覽。知道有什麼新能力。

#6  my-claude-devteam               P7/P9/P10方法論
    重點：研究其Agent定義和Hook配置
    方法：讀源碼配置，提取可複用模式。

產出：Agent工程筆記 + cc-platform Agent配置
```

### Phase 4 — 源碼級掌握（Day 29-36）

```
#7  luyao618 源碼分析               帶著實戰問題精讀
    重點模塊：Task→Tool→QueryEngine→query→Plugin→Hook
    方法：只讀你實戰中碰到問題的模塊。不全讀。

#8  FlorianBruniaux Guide           架構參考手冊
    查閱：壓縮流水線、權限7層、安全威脅
    方法：作為參考書，不是教程。

#9  VILA-Lab 學術論文               設計哲學
    重點：5 Values→13 Principles
    方法：精讀第一章和最後一章。

#10 yaniv-golan 內部架構            精確查詢
    方法：需要查特定文件/函數時才用。

產出：6張架構圖（循環/工具/上下文/權限/Hook/PC↔雲）
```

### Phase 5 — 平台發布（Day 37-44）

```
#11 everything-claude-code-zh       參考黑客松冠軍配置
    重點：提取可複用的Agent/Skill模板

#12 awesome-claude-code             生態探索
    重點：找競品平台，看別人怎麼打包分發

#13 整合 + 發布
    產出：cc-platform v1.0（Skills+Hooks+Plugin+MCP+文檔）
```

---

## 四、時間線

```
Phase 1 — 認知地圖        3天     luongnv89 + SeeingLikeAnAgent
Phase 2 — 實戰構建       17天     cc-self-train 10模塊
Phase 3 — Agent工程       8天     HarnessPatterns + SF2026 + P7/P9/P10
Phase 4 — 源碼掌握        8天     luyao618 + FlorianBruniaux + VILA-Lab
Phase 5 — 平台發布        8天     整合 + 發布

44天 ≈ 9週 ≈ 2個月 @ 1h/天
```

## 五、驗證：你的目標 vs 路線圖

```
你的目標                       路線圖覆蓋
─────────────────────────────────────────────
深度學習CC原理                  Phase 1-4 全覆蓋
以CC為核心構建平台              Phase 2 + Phase 5 產出
Agent工程化能力                 Phase 3 專門覆蓋
源碼級理解                      Phase 4 專門覆蓋
產出通用技能+插件               Phase 2 每個模塊都有產出
公開發布平台                    Phase 5 最終產出
```
