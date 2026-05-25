# CC 研究資源總索引

> 最後更新: 2026-05-25

---

## 1. 源碼

| Repo | Stars | 說明 |
|------|-------|------|
| anthropics/claude-code | 125K | 官方 repo，文檔/工作流/插件 |
| claude-code-best/claude-code | — | 逆向工程源碼 v2.4.4，54萬行 TS，可構建 |
| jengzang/ccSource | 12 | npm source map 鏡像 |
| MohammedAl-sultani/claude-code-source | 1 | 完整源碼 2026-03-31 |

## 2. 架構分析

| Repo | Stars | 說明 |
|------|-------|------|
| liuup/claude-code-analysis | 2.6K | CC 全面分析 |
| Windy3f3f3f3f/how-claude-code-works | 2.4K | 15篇架構深潛，中英雙語 |
| openedclaude/claude-reviews-claude | 1.4K | 17章 CC 審查自己源碼 |
| VILA-Lab/Dive-into-Claude-Code | 1.2K | 學術論文級，arXiv:2604.14228 |
| 6551Team/claude-code-design-guide | 808 | 46架構專題 |
| jiji262/build-code-agent | 605 | 從零構建 Code Agent |
| ThreeFish-AI/analysis_claude_code | 295 | 逆向工程研究 |
| waiterxiaoyy/Deep-Dive-Claude-Code | 268 | 13章逐層拆解 |
| alchaincyf/...-orange-book | 63 | 橙皮書系列 |

## 3. 從零構建

| Repo | Stars | 說明 |
|------|-------|------|
| Windy3f3f3f3f/claude-code-from-scratch | 1.2K | ~4000行 TS/Python，11章 |
| ProjectBarks/gopher-code | 1K | Go 重寫 |
| ConardLi/easy-agent | 705 | 完全重現 |
| zengyi-thinking/mini-claude | — | 2.5K行精簡 TS |
| zengyi-thinking/mini-claude-cpp | — | 2.2K行 C++ |
| funAgent/build-claude-code-cli | 57 | 49課拆解 |
| woodx9/build-your-claude-code-from-scratch | 156 | 從零構建教程 |
| KeWang0622/agent-zero-to-hero | 17 | 7週課程，19章，~4500行 Python |

## 4. 技能/插件生態

| Repo | Stars | 說明 |
|------|-------|------|
| hesreallyhim/awesome-claude-code | 44K | Skills/Hooks/Plugins 總索引 |
| VoltAgent/awesome-claude-code-subagents | 20K | 100+ subagents |
| travisvn/awesome-claude-skills | 12K | Skills 大全 |
| rohitg00/awesome-claude-code-toolkit | 1.7K | 135 agents + 35 skills |
| jackculpan/claude-skills-curated | 54 | 精選 Skills |

## 5. 開源競品

| Repo | Stars | 說明 |
|------|-------|------|
| anomalyco/opencode | 162K | 開源 coding agent，Effect-TS |
| deepelementlab/clawcode | 200 | Python+Rust agent |
| lingcoder/crab-code | 67 | Rust 精簡 CC 替代 |

## 6. 工程化標準

| Repo | Stars | 說明 |
|------|-------|------|
| shanraisshan/claude-code-best-practice | 54K | vibe coding → agentic engineering |
| josix/awesome-claude-md | 328 | CLAUDE.md 範例+模板+最佳實踐 |
| abhishekray07/claude-md-templates | 220 | CLAUDE.md 模板 |
| jrenaldi79/harness-engineering | 61 | 上下文工程 + 20+ 最佳實踐 |
| MuhammadUsmanGM/claude-code-best-practices | 24 | CC 最佳實踐 Wiki |
| leighstillard/claude.md-boilerplate | 8 | 工程化 CLAUDE.md 模板 |

## 7. 中文教學

| Repo | Stars | 說明 |
|------|-------|------|
| chemark/claude-code-learning | 22 | 系統化中文教程 |
| original4422/learn-claude-code | 11 | 結構化課程 |

## 8. CC 自身工程標準

```
Runtime:     Bun
語言:        TypeScript strict (零類型錯誤)
Lint:        Biome (recommended 基線)
提交:        Conventional Commits + husky + lint-staged
CI/CD:       GitHub Actions (lint + build + test)
構建:        build.ts → Bun.build() splitting
測試:        bun:test + 2,000+ 測試文件
Monorepo:    17 packages, Bun workspaces
Feature:     65+ 編譯時 flags
門禁:        bun run precheck (typecheck + lint + test)
```

## 9. 你的 Forks

| Repo | 用途 |
|------|------|
| ApeInspire/scout-research | 研究輸出 |
| ApeInspire/claude-code-1 | 源碼 v2.4.4 (主研究) |
| ApeInspire/how-claude-code-works | 架構分析 |
| ApeInspire/claude-reviews-claude | 元分析 |
| ApeInspire/Dive-into-Claude-Code | 學術分析 |
| ApeInspire/claude-code-design-guide | 設計指南 |
| ApeInspire/build-code-agent | 從零構建 |
| ApeInspire/analysis_claude_code | 逆向工程 |
| ApeInspire/opencode | 開源競品 |
| ApeInspire/claude-code | 官方鏡像 |
