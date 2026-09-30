<div align="center">

# 🧠 Awesome AI Ecosystem CN

**63 个 AI 生态核心项目的中文速览索引 —— 一份"会自己维护自己"的 awesome list**

*A self-maintaining, offline-first Chinese index of 63 hand-picked GitHub projects: AI dev tools · agent skills · platforms · learning resources.*

![Projects](https://img.shields.io/badge/收录项目-63-0969da) ![Static](https://img.shields.io/badge/纯静态-零依赖-2da44e) ![Offline](https://img.shields.io/badge/离线可用-双击即开-8250df) ![Maintained](https://img.shields.io/badge/维护方式-Agent_Skill_流水线-f0883e) [![M8ven Score](https://m8ven.ai/badge/mcp/novaapex-awesome-ai-ecosystem-cn-1wh55i?v=b6fdf6c4f03f0485fafa8ac89be9b7d6)](https://m8ven.ai/mcp/novaapex-awesome-ai-ecosystem-cn-1wh55i)

[📖 在线阅读](https://novaapex.github.io/awesome-ai-ecosystem-cn/) · [⬇️ 下载单文件](./github.html) · [🤖 维护流水线](./skills/manage-skill/SKILL.md)

</div>

---

## 🤔 为什么有这个仓库

调研 AI 生态项目的人都知道，痛点从来不是"找不到"，而是：

- **收藏了 = 再也没打开过**——README 又长又英文，每个项目重读一遍成本太高
- **星数会骗人**——真正决定选型的是 License、维护活跃度、最小可运行用法，而这些恰恰最难找全
- 收藏散落在书签、笔记、聊天记录里，**无法检索**

这个仓库的解法：把"读过一个项目"的产出**压缩成一张 5 分钟读完的中文卡片**，再把所有卡片汇成一份可搜索、可离线的单文件网页。更重要的是——**维护这套卡片的流程本身，也被工程化成了一个 Agent Skill**。

## 📖 这是什么

一个纯静态单文件 **`github.html`**，63 张项目卡片，每张固定五段结构：

> **定位**（是什么、解决什么问题）→ **能力/特性** → **用法**（最小可运行示例）→ **要点**（License、Star/Fork + 取数日期、踩坑记录）

三条内容纪律：

1. **事实红线**：所有数字与命令只来自项目 README 原文与 GitHub API，禁止 AI 转述编造，拿不准就标"待核实"
2. **数据带日期**：Star/Fork 等统计必须注明取数日期，过期数据通过"对比更新"机制刷新
3. **零基础友好**：术语首次出现给括号解释（如"CI（持续集成：提交代码后自动构建/测试的流程）"），命令看不懂可跳过，不影响理解

## ✨ 网页特性

- 🔍 **全文搜索**：项目名 / 仓库名 / 简介 / 技术词即时过滤，实时匹配计数
- 🗂️ **五大分类折叠**：分类标题即目录，导航 chips 带组内实时计数
- 🆕 **本周新增速览**：自动渲染本周收录（自然周口径，周一起算），chip 悬停显示一句话钩子 + 收录日期（今天/昨天/周X），新条目自动挂 NEW 徽标——零手工维护
- 🎯 **精准跳转**：速览与目录点击直达卡片，自动展开分区、平滑滚动、闪烁定位
- 📱 **响应式 + 零依赖**：桌面/移动自适应，双击即开，断网可用

## 🤖 核心差异：这份索引"会自己维护"

与其他 awesome list 最大的不同：**维护流程被写成了一条可审计的 Agent Skill 流水线**（[`skills/manage-skill`](./skills/manage-skill/SKILL.md)）。给 AI 助手一个 GitHub URL，它按六步执行，关键节点有人工确认卡点：

```text
GitHub URL
   │
   ▼
① 查重 ──── 已收录 → 对比更新分支（只做增量补充，统计换新取数日期）
   │ 新项目
   ▼
② 调研（README + GitHub API 双源核验）
   ▼
③ 提案：完整卡片 + 分类 + 插入位置 ── 用户逐项确认，不确认不落库
   ▼
④ 备份：持久目录保留最近 3 份，重名禁覆盖，先校验后写入
   ▼
⑤ 落库：插入卡片 + 同步分类计数与总数
   ▼
⑥ Gate 审查：可读性 / 事实红线 / HTML 结构 / 页面资产完整性
```

这套流程经过**四轮实战迭代**：从"查重后才允许调研"、提问式确认清单、备份轮转与标准回滚流程，到页面结构资产地图与折叠锚点跳转的踩坑记录——`manage-skill` 本身就是一份"AI 长期维护单文件项目"的实战手册，欢迎借鉴到你自己的仓库。

## 🚀 快速开始

**✨ 在线预览（无需下载）**：**[GitHub Pages 实时版 →](https://novaapex.github.io/awesome-ai-ecosystem-cn/)**

```bash
git clone https://github.com/NovaApex/awesome-ai-ecosystem-cn.git
```

双击 `github.html` 即可，无需服务器、无需联网。

> 💡 顶部搜索框可当"工具速查表"用：想找某类工具（如 `docker`、`MCP`、`TypeScript`）直接搜。
> 注：GitHub 网页上直接查看 `github.html` 会显示源码而非渲染效果，请下载后本地打开或走在线版。

## 🗂️ 仓库结构

```text
├── github.html           # 全部内容：63 张卡片 + 搜索 + 本周新增速览（单文件）
├── index.html            # 在线版跳转
├── skills/
│   └── manage-skill/     # 维护流水线：SKILL.md（流程）+ gate.md（审查标准）
└── README.md
```

## 🧭 分类速览（63 个项目，截至 2026-09-30）

| 分类 | 数量 | 收录逻辑 |
|---|---:|---|
| 🛠️ AI 开发工具与运行环境 | 14 | 让 AI Agent 干活的基建：浏览器控制、代码审查、长期记忆、云开发环境 |
| 🧰 领域专用工具 | 6 | 逆向、语音、视觉、法律基准等垂直领域利器 |
| 🧩 Agent 技能、插件与组件 | 19 | 给编码 Agent 装专业技能：设计品味、安全审计、上下文治理、CAD 生成 |
| 🌐 平台与框架 | 16 | Agent 治理与编排：多 Agent 管理、评估体系、控制平面 |
| 📚 学习资料与方法论 | 8 | 体系化知识：框架演进、方法论、实践指南 |
| **合计** | **63** | |

## 🤝 参与收录

- 发现值得收录的项目？[提个 Issue](https://github.com/NovaApex/awesome-ai-ecosystem-cn/issues) 留下仓库地址即可
- **收录标准**：官方文档可查证、对开发者有实际价值、与 AI 工具链 / Agent 生态 / 开发效率相关
- **AI 自动收录**：把仓库 URL 丢给接入了 `manage-skill` 的 AI 助手，流水线自动跑完六步
- **手动 PR**：卡片格式见 [SKILL.md「统一格式规范」](./skills/manage-skill/SKILL.md)，五段结构 + 五个 data 属性缺一不可
- Star 数、版本号过期或事实有误，同样欢迎指出

## 📄 License

**[CC0-1.0](LICENSE)** —— 自由使用、转载与二次整理，无需署名。

---

<div align="center">

**⭐ 持续更新中 · 由 [manage-skill](skills/manage-skill/SKILL.md) 驱动维护**

</div>
