# CC 研究資源總索引 v2 — 交叉驗證版

> 數據源：GitHub 搜索 + Web 搜索 + 源碼驗證
> 驗證方法：多源交叉確認，標註置信度

---

## 置信度分級

| 級別 | 含義 |
|------|------|
| ★★★ | 官方文檔或源碼直接確認 |
| ★★☆ | 多個獨立來源一致確認 |
| ★☆☆ | 單一來源，待驗證 |

---

## 一、官方資源 ★★★

| 資源 | 說明 |
|------|------|
| [code.claude.com/docs](https://code.claude.com/docs) | Agent SDK 官方文檔，Agent Loop 詳解 |
| [anthropics/claude-code](https://github.com/anthropics/claude-code) | 官方 repo，125K★ |

## 二、源碼 ★★★

| 資源 | Stars | 說明 |
|------|-------|------|
| [claude-code-best/claude-code](https://github.com/claude-code-best/claude-code) | — | v2.4.4，54萬行，可構建。51.3萬行TS，1,902源文件，25模塊 |
| [jengzang/ccSource](https://github.com/jengzang/ccSource) | 12 | npm source map 鏡像 |

## 三、架構分析（按深度排序）★★★

| 資源 | Stars | 深度 | 最適合 |
|------|-------|------|--------|
| [FlorianBruniaux/claude-code-ultimate-guide](https://github.com/FlorianBruniaux/claude-code-ultimate-guide) | 新 | 全景 | **Day1 首選** — 最完整單頁架構參考 |
| [luyao618/Claude-Code-Source-Study](https://github.com/luyao618/Claude-Code-Source-Study) | 新 | 逐行 | 25篇中文深潛，逐文件逐函數 |
| [alejandrobalderas/claude-code-from-source](https://github.com/alejandrobalderas/claude-code-from-source) | 新 | 全書 | 18章英文書，400頁 |
| [Windy3f3f3f3f/how-claude-code-works](https://github.com/Windy3f3f3f3f/how-claude-code-works) | 2.4K | 源碼級 | 15篇深潛 + 4000行復現 |
| [openedclaude/claude-reviews-claude](https://github.com/openedclaude/claude-reviews-claude) | 1.4K | 元分析 | 17章，CC 審查自己 |
| [VILA-Lab/Dive-into-Claude-Code](https://github.com/VILA-Lab/Dive-into-Claude-Code) | 1.2K | 學術級 | arXiv:2604.14228 |
| [6551Team/claude-code-design-guide](https://github.com/6551Team/claude-code-design-guide) | 808 | 全景 | 46架構專題 |
| [HZ0108/Inside-Claude-Code-Architecture](https://github.com/HZ0108/Inside-Claude-Architecture-and-Design-Philosophy) | 新 | 子系統 | 10份PDF，子系統隔離分析 |

## 四、實戰教程 ★★☆

| 資源 | 說明 |
|------|------|
| [sjnims/plugin-dev](https://github.com/sjnims/plugin-dev) | **必裝** — CC 插件開發工具包，10 skills + 3 agents |
| [Neha/skill-starter-template](https://github.com/Neha/skill-starter-template) | Skill 模板，跨工具兼容 |
| [coder/skills](https://github.com/coder/skills) | Agent Skills 範例集合 |
| [Jamie-BitFlight/claude_skills](https://github.com/Jamie-BitFlight/claude_skills) | 社區插件合集（含 development-harness） |
| [Apidog: Build Your Own CC](https://apidog.com/blog/build-your-own-claude-code/) | 200行 Python 最小復現 |
| [Sherlock: How to Write Skills](https://sherlock.xyz/post/how-to-write-skills-for-claude-code-and-cowork) | Skill 寫作最佳實踐 |

## 五、中文深度資源 ★★☆

| 資源 | 說明 |
|------|------|
| [CSDN: 50萬行源碼拆解](https://grapecity.csdn.net/6a0e6fcc662f9a54cb7606ad.html) | 工業級 Agent 架構分析 |
| [阿里雲: Plugin 系統拆解](https://developer.aliyun.com/article/1736450) | 6大組件深度拆解 |
| [騰訊雲: 核心架構參考](https://cloud.tencent.com.cn/developer/article/2648848) | 架構全景 |
| [luyao618/Claude-Code-Source-Study](https://github.com/luyao618/Claude-Code-Source-Study) | 25篇逐行分析 |
| **出版書籍** [Claude Code 實戰](https://m.epubit.com/bookDetails?id=UB94158012f88a6) | ISBN 978-7-115-69653-3，2026年5月 |

## 六、開源競品 ★★★

| 資源 | Stars | 說明 |
|------|-------|------|
| [anomalyco/opencode](https://github.com/anomalyco/opencode) | 162K | Effect-TS 架構 |

## 七、從零構建 ★★☆

| 資源 | Stars | 說明 |
|------|-------|------|
| [Windy3f3f3f3f/claude-code-from-scratch](https://github.com/Windy3f3f3f3f/claude-code-from-scratch) | 1.2K | ~4000行 TS/Python |
| [zengyi-thinking/mini-claude](https://github.com/zengyi-thinking/mini-claude) | — | 2.5K行最簡 TS |

## 八、工程化標準 ★★☆

| 資源 | Stars | 說明 |
|------|-------|------|
| [shanraisshan/claude-code-best-practice](https://github.com/shanraisshan/claude-code-best-practice) | 54K | agentic engineering |
| [josix/awesome-claude-md](https://github.com/josix/awesome-claude-md) | 328 | CLAUDE.md 範例合集 |

## 九、生態總覽 ★★★

| 資源 | Stars | 說明 |
|------|-------|------|
| [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | 44K | 生態總索引 |
| [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) | 12K | Skills 大全 |
| [VoltAgent/awesome-claude-code-subagents](https://github.com/VoltAgent/awesome-claude-code-subagents) | 20K | 100+ subagents |

---

## 交叉驗證：關鍵事實確認

| 事實 | 源碼 | 分析 repo | 官方文檔 | 置信度 |
|------|------|-----------|---------|--------|
| Agent 循環 = while loop | ✓ | ✓ 5+來源 | ✓ | ★★★ |
| 雙層生成器（QE + query） | ✓ | ✓ | ✓ | ★★★ |
| 98.4% 基礎設施 | ✓ | ✓ VILA-Lab | — | ★★☆ |
| 7層權限 | ✓ | ✓ 5+來源 | ✓ | ★★★ |
| 4-5級壓縮 | ✓ | ✓ | ✓ | ★★★ |
| 27 Hook 事件 | ✓ | ✓ | — | ★★☆ |
| 10 Plugin 組件 | ✓ | ✓ | ✓ | ★★★ |
| buildTool fail-closed | ✓ | ✓ | — | ★★☆ |
| ToolUseContext 60+字段 | ✓ | ✓ | — | ★★☆ |
| 子Agent 零上下文繼承 | ✓ | ✓ 3+來源 | ✓ | ★★★ |
| 流式工具預執行 | ✓ | ✓ | — | ★★☆ |
| 記憶不依賴向量庫 | ✓ | ✓ 3+來源 | — | ★★☆ |
