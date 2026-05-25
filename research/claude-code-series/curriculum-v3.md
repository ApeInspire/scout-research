# CC 專家課程 v3 — 第三角度審計版

> v1 問題：碎片練習，無回顧
> v2 問題：架構和實踐分離，學架構時不寫代碼，寫代碼時不懂架構
> v3 修正：架構與實踐每週同步交織

---

## 審計發現：v2 的根本缺陷

v2 的結構：
```
Phase 1 Skill  → Phase 2 Hook → Phase 3 架構 → Phase 4 平台
```

問題：Phase 1-2 你不懂架構，寫的 Skill/Hook 是盲目的。
      Phase 3 你不寫代碼，學的架構是抽象的。
      Phase 4 才開始平台，太晚了。

**正確的方式：每週同時推進架構理解和實踐構建，互相餵養。**

---

## 新的設計原則

1. **架構與實踐同步**：每週一個架構主題 + 一個實踐項目，互相關聯
2. **平台從第一天開始**：不是最後才做。Day1 就建 repo，每天往裡加東西
3. **你的日常 CC 使用 = 實驗室**：你今天用 CC 時觀察到的行為 → 晚上讀源碼驗證 → 第二天改進
4. **每周產出一個可發布的東西**：不是練習，是真實產出

---

## Phase 1 — 工具層（第1-14天）

> 架構主題：Tool 系統
> 實踐項目：Skill Pack（5個 Skill）
> 關聯：理解 Tool 接口 → 理解 Skill 如何變成 Tool → 寫更好的 Skill

### Week 1 — 工具接口（第1-7天）

**Day 1-2：Tool 系統架構 + Skill 觀察**
- 架構：讀 `Tool.ts`（814行），理解 Tool 接口的結構
- 實踐：讀 10 個熱門 Skill，用 Tool 接口的知識重新審視它們
- 問題：Skill 調用時，CC 內部發生了什麼？
- 產出：Tool 接口 × Skill 的對應關係圖

**Day 3-4：寫 Skill + 讀 tools.ts**
- 架構：讀 `tools.ts`，理解 getAllBaseTools() → getTools() → assembleToolPool() 三層裝配
- 實踐：寫 2 個 Skill，使用 `allowedTools` 限制工具
- 問題：`allowedTools` 怎麼過濾掉不需要的工具？
- 產出：2 個 Skill + 工具裝配流程圖

**Day 5-6：buildTool 工廠 + 寫參數化 Skill**
- 架構：理解 buildTool() 的 7 個 fail-closed 默認值
- 實踐：寫 2 個參數化 Skill
- 問題：如果你要給 CC 加一個新工具，buildTool 怎麼幫你？
- 產出：2 個參數化 Skill

**Day 7：回顧**
- 回顧：Tool 系統的 3 層裝配 + 你的 4 個 Skill
- 改進早期 Skill
- 產出：Skill Pack v0.5

### Week 2 — 工具執行（第8-14天）

**Day 8-9：ToolUseContext + Skill 注入機制**
- 架構：讀 `ToolUseContext`（60+字段），理解一個工具執行時能訪問什麼
- 實踐：讀 `loadSkillsDir.ts`，理解 Skill .md → Command → 系統提示詞
- 問題：Skill 的描述是怎麼到 AI 面前的？
- 產出：Skill 加載流程圖

**Day 10-11：query() + Skill 在循環中的位置**
- 架構：讀 `query.ts` 的 9 步流水線，定位 Skill 在每一步的作用
- 問題：Skill 調用觸發了 9 步中的哪幾步？
- 產出：Agent 循環中標註 Skill 位置

**Day 12-13：組合 Skill + 架構復用**
- 實踐：寫一個工作流 Skill 組合（3個Skill協作）
- 架構：用 Tool 系統知識優化 Skill 的 allowedTools 配置
- 產出：Skill 組合 + 優化後的 Skill Pack

**Day 14：回顧**
- 回顧：Tool 系統完整理解 + Skill Pack v1.0
- 發布 Skill Pack 到 GitHub
- 產出：cc-skills repo v1.0

---

## Phase 2 — 事件層（第15-28天）

> 架構主題：Hook 系統 + 權限系統
> 實踐項目：Hook Pack（4個 Hook）
> 關聯：理解事件流 → 理解攔截點 → 寫精準的 Hook

### Week 3 — Hook 機制（第15-21天）

**Day 15-16：Hook 架構 + 觀察**
- 架構：讀 `src/hooks/` 核心文件，理解 27 個事件
- 實踐：在 CC 中啟用官方範例 Hook，觀察觸發時機
- 產出：27 事件分類圖

**Day 17-18：PreToolUse + PostToolUse**
- 架構：理解 Hook 的執行上下文和權限
- 實踐：寫 PreToolUse Hook（攔截 Bash）+ PostToolUse Hook（格式化）
- 產出：2 個 Hook

**Day 19-20：Hook 鏈 + Skill**
- 架構：理解多個 Hook 的執行順序
- 實踐：寫一個觸發 Skill 的 Hook
- 產出：Hook→Skill 觸發器

**Day 21：回顧**

### Week 4 — 權限 + 深化（第22-28天）

**Day 22-23：權限系統架構**
- 架構：讀 `permissions/`，理解 7 層防禦 + deny-first
- 問題：Hook 的權限檢查在第幾層？
- 產出：權限 × Hook 交叉圖

**Day 24-25：Hook 源碼深潛**
- 架構：讀 `src/hooks/` 完整實現
- 理解 Hook 註冊→觸發→執行→返回 的完整鏈路
- 產出：Hook 生命週期圖

**Day 26-27：複雜 Hook**
- 實踐：寫一個轉換型 Hook（修改工具輸入/輸出）
- 架構：用權限知識確保 Hook 安全
- 產出：轉換型 Hook

**Day 28：回顧**
- Hook Pack v1.0 + 發布
- 用 Phase 1 的 Tool 知識回顧 Hook——Hook 攔截的到底是 Tool 的哪個階段？

---

## Phase 3 — 核心循環（第29-42天）

> 架構主題：Agent 循環 + 上下文工程
> 實踐項目：Plugin + 架構圖集
> 關聯：理解全貌 → 理解你的 Skill/Hook 在整個系統中的位置

### Week 5 — Agent 循環（第29-35天）

**Day 29-31：雙層生成器**
- 架構：讀 QueryEngine.ts + query.ts
- 關鍵：用 Phase 1-2 的實踐經驗重新審視——Skill 調用時，循環的每一步在做什麼？
- 產出：Agent 循環完整架構圖

**Day 32-33：恢復策略**
- 架構：7 種恢復策略，何時觸發，如何恢復
- 產出：恢復策略決策樹

**Day 34-35：回顧**
- Agent 循環 + 恢復策略圖
- 將 Skill/Hook 在圖上標註位置

### Week 6 — 上下文 + 平台雛形（第36-42天）

**Day 36-38：上下文工程**
- 架構：4-5 級壓縮流水線 + 緩存策略
- 問題：壓縮對 Skill 的行為有什麼影響？
- 產出：上下文裝配 + 壓縮流程圖

**Day 39-40：PC↔雲邊界**
- 架構：本地執行 vs 雲端推理的完整邊界
- 問題：Hook 全在本地，Skill 提示詞注入也是本地——這意味著什麼？
- 產出：PC↔雲邊界圖

**Day 41-42：回顧**
- 6 張架構圖完成
- 用架構知識重新審視 Skill Pack + Hook Pack
- 發布架構圖集 v1.0

---

## Phase 4 — 平台構建（第43-56天）

> 架構主題：Plugin + MCP
> 實踐項目：平台 v1.0
> 關聯：用全部所學構建完整平台

### Week 7 — Plugin + MCP（第43-49天）

**Day 43-45：Plugin 架構**
- 架構：讀 `plugins/` + `types/plugin.ts`
- 實踐：把你的 Skill Pack + Hook Pack 打包成一個 Plugin
- 產出：Plugin v0.1

**Day 46-48：MCP 架構**
- 架構：讀 `services/mcp/`，7 種傳輸
- 實踐：寫一個 MCP Server，為平台提供外部工具
- 產出：MCP Server v0.1

**Day 49：回顧**

### Week 8 — 平台發布（第50-56天）

**Day 50-52：平台整合**
- Skill Pack + Hook Pack + Plugin + MCP = 一個安裝包
- 統一入口、安裝腳本、使用文檔

**Day 53-54：競品對比**
- 讀 OpenCode 架構，對比 CC
- 用 8 週的知識形成自己的判斷

**Day 55-56：發布 + 總結**
- 平台 v1.0 公開發布
- CC 專家學習總結：我學到了什麼，我構建了什麼

---

## 總時間線

```
Phase 1 — 工具層     14天    Tool 架構 + Skill Pack v1.0
Phase 2 — 事件層     14天    Hook 架構 + Hook Pack v1.0
Phase 3 — 核心層     14天    6 張架構圖 + 深層理解
Phase 4 — 平台層     14天    Plugin + MCP + 平台 v1.0

56天 ≈ 2.5個月 @ 1h/天
每週：架構主題 + 實踐項目，同步推進
```

## v3 vs v2 的本質差異

```
v2                           v3
─────────────────────────    ─────────────────────────
Phase 1-2 純實踐（盲目）     每週同時學架構+實踐（互相餵養）
Phase 3 純架構（抽象）       架構用實踐經驗來理解
Phase 4 才開始平台           Day1 就建 repo，每天往裡加
練習項目（做完就扔）         真實項目（Skill Pack 從 v0.5→v1.0）
無日常使用反饋               每天用 CC = 實驗室
```

## 每日結構

```
30min — 架構    讀當週架構主題的源碼
25min — 實踐    基於架構理解，構建/改進當天的產出
 5min — 連接    一句話：今天學的架構知識如何改變了我的實踐？
```
