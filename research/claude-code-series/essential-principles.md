# 核心原則 — 雙過濾器篩選結果

> 過濾器1：第一性原理（所有Agent系統都必須面對的問題）
> 過濾器2：AI進化免疫（一年內AI無法替代）
> 雙過濾後：只保留無法被淘汰的知識

---

## 過濾過程

```
原始素材      35 資源 · 44 天課程
              │
第一性過濾    淘汰：CC 命令、API 參數、Prompt 技巧、實現細節
              │      UI、工作流、配置格式、具體工具名稱
              │
AI進化過濾    淘汰：模型限制分析、性能優化技巧、當前最佳實踐
              │     平台特有功能、特定版本特性
              │
剩餘          7 個原則
```

---

## 7 個核心原則

### 1. Agent 的原子結構

```
Agent = while loop + tool calling

不是：複雜編排、意圖分類、DAG、RAG、Planner/Executor 分離
就是：模型決定一切。循環調用工具。直到模型認為完成了。

為什麼是原子結構：這是 Agent 的最簡定義。換任何語言、任何平台、任何模型，都是這個結構。
源頭：CC 源碼 query.ts + VILA-Lab arXiv + alejandrobalderas 全書
```

### 2. 接口分離

```
Tool 接口 = AI 和世界之間唯一的接觸面

Tool 定義了"AI 能做什麼"。
接口穩定 → 實現可任意替換。
接口設計決定整個系統的擴展性。

為什麼不會被淘汰：只要 AI 需要調用外部工具，就需要接口。
源頭：CC 源碼 Tool.ts + "Seeing Like an Agent" 官方博客
```

### 3. 安全的結構性約束

```
安全 ≠ 檢查點。安全 = 結構屬性。

deny > allow（否決權永遠高於允許權）
權限不跨會話恢復（每輪重建信任）
默認不安全（fail-closed）

為什麼不會被淘汰：AI 越強，這些約束越重要。不是能力問題，是權力問題。
源頭：CC 源碼 permissions/ + VILA-Lab 安全章節 + FlorianBruniaux CVE 庫
```

### 4. 上下文的經濟學

```
上下文 = 稀缺資源。管理 ≠ 擴充窗口。

分層壓縮：最便宜的先做，逐步升級
緩存策略決定成本邊界
上下文放置位置決定緩存效率

為什麼不會被淘汰：上下文永遠有限。壓縮永遠需要。Cache 永遠比 API 便宜。
源頭：CC 源碼 context/ + VILA-Lab + alejandrobalderas 第 8 章
```

### 5. 擴展的分層

```
不同擴展方式的代價不同。分層 = 給用戶選擇。

文字注入（Skill）：最輕。0 計算。破壞 cache。
事件攔截（Hook）：0 token。本地執行。不破壞 cache。
打包分發（Plugin）：組合以上兩者 + 外部工具。
協議接入（MCP）：最重。外部依賴。最強能力。

為什麼不會被淘汰：這些分層對應不同的成本和安全約束。AI 再強也繞不開。
源頭：CC 擴展系統 + Build Your Own Agent (VILA-Lab) + Agentic Harness Patterns
```

### 6. 隔離與組合

```
子 Agent = 隔離的上下文 + 自包含的任務

隔離保證安全（子 Agent 的錯誤不污染父 Agent）
自包含保證可組合（任何 Agent 可以調用任何其他 Agent）
協調開銷 > 5 Agent 時超過生產力

為什麼不會被淘汰：複雜任務的分解和隔離是計算機科學的永恆問題。
源頭：CC 源碼 AgentTool/ + addyosmani Agent Teams + my-claude-devteam
```

### 7. 少框架，多模型

```
信任 AI 的推理。不建複雜編排。

不建：意圖分類器、任務路由器、DAG 編排器、Planner/Executor
交互：AI 自己決定調什麼工具、什麼時候停、下一步做什麼

為什麼不會被淘汰：AI 模型能力在增長。框架越薄，越能利用模型進步。
源頭：Anthropic 官方設計哲學 + Seeing Like an Agent + VILA-Lab 5 Values
```

---

## 學習節奏

```
每天 1 個原則。7 天完成。

Day 1  原則 1：Agent 原子結構      → 手繪 while loop
Day 2  原則 2：接口分離             → 畫 Tool 接口圖
Day 3  原則 3：安全結構約束          → 畫 deny-first 模型
Day 4  原則 4：上下文經濟學          → 優化 CLAUDE.md
Day 5  原則 5：擴展分層             → 畫四層擴展圖
Day 6  原則 6：隔離與組合           → 設計子 Agent
Day 7  原則 7：少框架多模型          → 審計你的 CC 配置

之後 → 基於這 7 個原則構建 cc-platform
```

## 持續驗證機制

```
每週：
  搜一次 "Claude Code architecture agent design 2026"
  檢查 7 個原則是否仍然成立
  發現新原則 → 加入。舊原則被證偽 → 淘汰。

每個原則的失效條件：
  - Agent 不再用 while loop（變成完全不同結構）
  - AI 不再需要外部工具（直接內化所有能力）
  - 安全不再需要 deny-first（但這需要信任 AI 100%）

目前三個都不成立。
```
