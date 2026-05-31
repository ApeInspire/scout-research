# CC 核心課程 — 只教不會過期的

> 每課三源交叉確認。全部核心原則。28天。

## Week 1 — Agent 系統設計原理

### Day 1：Agent 的本質
Agent = while loop + tool calling。CC 98.4%是基礎設施。
（來源：VILA-Lab + alejandrobalderas + FlorianBruniaux）
**你做**：手繪 Agent 交互鏈。

### Day 2：Tool 抽象
Tool 接口核心 3 方法。buildTool() 7 個默認全 fail-closed。
（來源：CC 源碼 Tool.ts + luyao618 + agentic-ai-from-cc）
**你做**：Tool 接口簡圖。

### Day 3：Agent 循環 9 步
AsyncGenerator。每步是失敗隔離點。
（來源：query.ts + luyao618 + yaniv-golan）
**你做**：9 步流水線圖。

### Day 4：安全 deny-first
7 層縱深。deny > allow。權限永不從會話恢復。
（來源：permissions/ + VILA-Lab + FlorianBruniaux）
**你做**：權限 7 層圖。

### Day 5：上下文分層壓縮
4-5 級。CLAUDE.md 放 message 不放 system prompt。
（來源：context/ + VILA-Lab + alejandrobalderas）
**你做**：優化 CLAUDE.md。

### Day 6-7：回顧 + OpenCode 對比

## Week 2 — 擴展機制

### Day 8：Skill = 文字注入
### Day 9：Hook = 0-token 攔截
### Day 10：Plugin = 打包分發
### Day 11：MCP = AI 的 TCP/IP
### Day 12-14：整合 + 回顧

## Week 3 — Agent 編排

### Day 15：子 Agent 上下文隔離
### Day 16-17：多 Agent 編排（3-5-6 法則）
### Day 18-19：6 個設計模式
### Day 20-21：回顧

## Week 4 — 發布

### Day 22-24：平台發布
### Day 25-26：CC vs OpenCode vs Codex CLI
### Day 27-28：畢業審計

## 10 個核心原則

1. Agent = while loop。98.4%基礎設施。
2. Tool 接口決定能力邊界。fail-closed。
3. 9 步循環，每步獨立恢復。
4. deny-first，7 層，權限不恢復。
5. 上下文分層壓縮。CLAUDE.md 保護 cache。
6. Skill 文字。Hook 攔截。Plugin 打包。MCP 外部。
7. 子 Agent 隔離。prompt 自包含。
8. 3-5-6 法則。>5 Agent = 開銷 > 產出。
9. AsyncGenerator。Fork 共享 cache。
10. 少框架，多模型。
