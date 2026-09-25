<div align="center">

# 📚 GitHub 项目简介索引

**把平时收集、调研过的 GitHub 项目，按统一格式整理成一份零基础友好的静态网页索引**

![Total Projects](https://img.shields.io/badge/收录项目-61-0969da) ![Static](https://img.shields.io/badge/纯静态-零依赖-2da44e) ![Offline](https://img.shields.io/badge/离线可用-双击即开-8250df) ![Maintained](https://img.shields.io/badge/AI技能自动维护-manage--skill-f0883e)

</div>

---

## 📖 这是什么

一份单文件的 GitHub 项目中文速览索引。每个项目一条折叠卡片，包含**仓库链接 / 定位 / 能力特性 / 用法示例 / 要点（含 License、Star 数据、踩坑记录）**，全部事实只来自项目 README 原文与官方 API，零基础也能看懂。

核心文件只有一个：**`github.html`** —— 纯静态、无依赖、离线可用，浏览器双击即开。

## ✨ 功能亮点

- 🔍 **全文搜索**：输入关键词即时过滤（匹配项目名 / 仓库名 / 简介 / 技术词），实时显示匹配计数
- 🗂️ **五大分类**：分类标题即目录，点击折叠/展开；顶部导航 chips 带组内实时计数
- 💡 **闪烁高亮**：点击目录项自动展开对应卡片并闪烁定位，页内精准跳转
- 📱 **自适应布局**：桌面/移动端均可阅读，回到顶部按钮随手可用
- 🛡️ **零基础友好**：专业术语首次出现给括号解释，命令看不懂可直接跳过，不影响理解项目

## 🚀 快速开始

1. 下载本仓库中的 `github.html`
2. 用任意现代浏览器打开即可（无需服务器、无需联网）
3. 顶部搜索框可当"工具速查表"用：想找某类工具（如 `docker`、`MCP`、`TypeScript`）直接搜

> 💡 注：GitHub 网页上直接查看 `github.html` 会显示源码而非渲染效果，请下载后本地打开。

## 📊 当前收录

共 **61** 个项目（截至 2026-09-25），持续更新中：

| 分类 | 数量 |
|---|---:|
| 🛠️ AI 开发工具与运行环境 | 14 |
| 🧰 领域专用工具 | 6 |
| 🧩 Agent 技能、插件与组件 | 18 |
| 🌐 平台与框架 | 15 |
| 📚 学习资料与方法论 | 8 |
| **合计** | **61** |

## 🤖 manage-skill：AI 自动维护体系

本仓库的日常维护由一个项目级 AI 技能托管：[`skills/manage-skill/`](skills/manage-skill/)。在 WorkBuddy 中打开本仓库工作区即可自动识别、按指令触发。

### 目录结构

```
skills/manage-skill/
├── SKILL.md            # 技能主文件：触发条件、操作步骤、统一格式规范
├── references/
│   └── gate.md         # 运行结果审查标准（质量门）
├── scripts/            # 脚本/代码库（预留）
└── assets/             # 素材库（预留）
```

### 两大功能

| 功能 | 触发条件 | 流程 |
|---|---|---|
| **① GitHub 项目记录** | 用户提及"记录"，或直接给出 GitHub 仓库地址 | ① 查重（已收录则告知所在分类）→ ② 访问仓库读取 README / License / Star 原文 → ③ 按统一格式生成条目并更新计数 |
| **② 内容质量审查** | `github.html` 内容发生改变后 | ① 读取 `references/gate.md` 审查标准 → ② 逐项审查，输出「通过 / 问题清单」 |

### gate.md 审查三大重点

1. **可读性** —— 一句话钩子 ≤ 40 字；专业术语首次出现给零基础解释；单条 4–10 个要点、约 150–600 字，长度合理
2. **内容质量** —— 定位 / 能力 / 用法 / 要点四段覆盖；事实来自原文不编造；Star 等数据必须带取数日期；仓库异常（停更、转载等）如实标注、不得美化
3. **HTML 结构** —— slug 唯一、四个 data 属性齐全、分类正确、计数同步、公共部分（样式/脚本）不得改动等 8 项硬性检查

## 📐 条目格式

每条记录 = 一个 `<details>` 折叠卡片，放入对应分类分区：

```html
<details id="markitdown" data-cat="dev" data-name="MarkItDown"
         data-repo="microsoft/markitdown" data-blurb="微软开源，把各种文件转成 Markdown 喂给 LLM">
<summary><b>MarkItDown</b> · <a href="https://github.com/microsoft/markitdown"><code>microsoft/markitdown</code></a>
  — 微软开源，把各种文件转成 Markdown 喂给 LLM</summary>

<ul>
<li><strong>定位</strong>：…（项目是什么、解决什么问题、面向谁）</li>
<li><strong>能力/特性</strong>：…（核心功能清单）</li>
<li><strong>用法</strong>：…（CLI / 配置 / 安装的最小可运行示例）</li>
<li><strong>要点</strong>：…（License、带取数日期的统计、坑与注意事项）</li>
</ul>

</details>
```

## 📝 维护约定

- 条目格式统一：折叠块 `<details>`（唯一 slug `id` + `data-cat/data-name/data-repo/data-blurb` 四属性）+ 摘要行 + 正文四段
- 所有命令、路径、版本号等事实**只来自 README 原文与官方 API**，不采用第三方转述
- 数字类信息（Star 数、版本号）必须标注取数日期
- 新增/删除条目后同步更新：对应分类 `<h2>` 计数、顶部总数

---

<div align="center">

**⭐ 持续更新中 · 由 [manage-skill](skills/manage-skill/SKILL.md) 驱动维护**

</div>
