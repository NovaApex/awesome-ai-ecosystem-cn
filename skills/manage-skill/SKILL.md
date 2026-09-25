---
name: manage-skill
description: github.html 项目索引管理技能——GitHub 项目记录入库与内容质量审查。当用户提及"记录"某个 GitHub 项目、直接给出 GitHub 仓库地址，或 github.html 内容发生改变需要质量审查时使用。
---

# manage-skill — github.html 项目索引管理

## 管理对象

`D:/Project/workbuddy/github-manager/github.html`（GitHub 项目中文速览索引，单文件 HTML，含搜索/分类导航/折叠详情）

## 统一格式规范（入库条目必须遵守）

每条记录 = 一个 `<details>` 折叠块，放入对应分类分区 `<section class="cat">` 内：

```html
<details id="英文短横线slug" data-cat="分类key" data-name="项目名" data-repo="owner/repo" data-blurb="一句话钩子">
<summary><b>项目名</b> · <a href="https://github.com/owner/repo"><code>owner/repo</code></a> — 一句话钩子</summary>

<ul>
<li><strong>定位</strong>：…（详情展开，首句不复写一句话钩子）</li>
<li><strong>能力/特性</strong>：…（可用 <code>code</code> 分隔的特性清单）</li>
<li><strong>用法</strong>：…（CLI / 配置 / 安装命令，命令放 <code>code</code> 或 <code>pre</code>）</li>
<li><strong>要点</strong>：…（License、Star/Fork 等统计数据需注明取数日期、坑与注意事项）</li>
</ul>

</details>
```

硬性要求：
1. `id` 为英文短横线 slug，全文件唯一（重复会被搜索脚本覆盖）
2. 四个 data 属性缺一不可：`data-cat` / `data-name` / `data-repo` / `data-blurb`
3. 分类 key 只有 5 个：`dev`（🛠️ AI 开发工具与运行环境）、`tool`（🧰 领域专用工具）、`skill`（🧩 Agent 技能、插件与组件）、`plat`（🌐 平台与框架）、`learn`（📚 学习资料与方法论）
4. 新增/删除条目后，必须同步更新：对应 `<h2>` 里的分类计数、顶部 `<blockquote>` 里的总数
5. 其他部分（`<style>`、搜索脚本、`<footer>` 维护说明）不要改动

---

## 功能 1：GitHub 项目记录

**启动条件**：用户提及"记录"某项目，或直接给出 GitHub 项目地址（`github.com/...`）。

**步骤**：
- **step1 查重**：在 github.html 中搜索该仓库（按 `data-repo`、`data-name`、正文关键词）。若已存在 → 告知用户已收录（指出所在分类），结束；不存在 → 继续。
- **step2 访问**：访问用户给出的 GitHub 项目地址，读取 README、License、Star/Fork 等关键信息。
- **step3 生成**：按上方「统一格式规范」生成新的 `<details>` 条目，判断正确分类，更新分类计数与总数，落库到 github.html。

## 功能 2：github.html 内容质量审查

**启动条件**：github.html 内容发生改变（新增/修改/删除条目）之后启动。

**步骤**：
- **step1**：阅读 `references/gate.md`，明确审查标准。
- **step2**：按 gate.md 标准对本次变更内容逐项审查，输出审查结果（通过 / 问题清单及修改建议）。

## 目录说明

- `scripts/` — 脚本/代码库（当前为空，预留）
- `references/gate.md` — 运行结果审查标准
- `assets/` — 素材库（当前为空，预留）
