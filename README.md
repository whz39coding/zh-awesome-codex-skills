# Awesome Codex Skills 中文版

> 本仓库是 [ComposioHQ/awesome-codex-skills](https://github.com/ComposioHQ/awesome-codex-skills) 的中文整理版本，面向中文 Codex 用户提供更容易阅读的技能索引、安装说明和核心技能简介。

<p align="center">
  <a href="https://dashboard.composio.dev/login?utm_source=Github&utm_medium=Youtube&utm_campaign=2025-11&utm_content=AwesomeCodexSkills">
    <img width="1280" height="640" alt="Composio banner" src="codex_cover_image.png">
  </a>
</p>

<p align="center">
  <a href="https://awesome.re">
    <img src="https://awesome.re/badge.svg" alt="Awesome" />
  </a>
  <a href="https://makeapullrequest.com">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="PRs Welcome" />
  </a>
</p>

一个实用 Codex Skills 清单，可用于 Codex CLI 和 Codex API 中的工作流自动化、写作、数据分析、代码迁移、协作工具连接等场景。

> 想让 Codex 不只是生成文本，而是能发邮件、建 issue、发 Slack、操作 Notion/GitHub 等应用？可以从 [connect/](./connect/) 开始了解。

## 版权与声明

- 原项目及原始内容版权归 [ComposioHQ/awesome-codex-skills](https://github.com/ComposioHQ/awesome-codex-skills) 及其贡献者所有。
- 本仓库仅做中文化整理、学习交流和国内使用便利化，不声称拥有原项目版权。
- 截至 2026-06-02，源仓库根目录未包含明确的 `LICENSE` 文件；因此本仓库不会额外声明开源许可证，也不会暗示原内容可被自由再授权。
- 如果原作者、贡献者或权利方认为本仓库内容存在不当转载、翻译或侵权，请通过 GitHub Issue 联系，确认后会及时修改或删除相关内容。
- 安装、使用第三方技能或外部服务时，请自行遵守对应项目、服务和 API 的许可证、服务条款与隐私规则。

## 快速开始

### 使用 Skill Installer 安装，推荐

```bash
git clone https://github.com/whz39coding/zh-awesome-codex-skills.git
cd zh-awesome-codex-skills

# 安装单个或多个 skill 到 $CODEX_HOME/skills，默认是 ~/.codex/skills
python skill-installer/scripts/install-skill-from-github.py --repo whz39coding/zh-awesome-codex-skills --path meeting-notes-and-actions
```

安装器会把指定 skill 放到 `$CODEX_HOME/skills/<skill-name>`。安装或更新后，重启 Codex 让新 metadata 生效。

### 手动安装

1. 把需要的 skill 文件夹复制到 `$CODEX_HOME/skills/`，默认是 `~/.codex/skills/`。
2. 重启 Codex。
3. 在新会话里直接描述任务，或明确提到 skill 名称；Codex 会根据 `SKILL.md` 里的 `description` 判断是否触发。

## 目录

- [Bernstein](https://github.com/chernistry/bernstein) - 多智能体编排器，带 Codex CLI 适配器，可在隔离 git worktree 中并行运行 Codex agent，并带质量门禁。
- [什么是 Codex Skills？](#什么是-codex-skills)
- [Skills](#skills)
  - [开发与代码工具](#开发与代码工具)
  - [效率与协作](#效率与协作)
  - [沟通与写作](#沟通与写作)
  - [数据与分析](#数据与分析)
  - [元工具与实用工具](#元工具与实用工具)
- [在 Codex 中使用 Skills](#在-codex-中使用-skills)
- [创建 Skills](#创建-skills)
- [贡献](#贡献)
- [社区与资源](#社区与资源)
- [同步策略](#同步策略)

## 什么是 Codex Skills？

Codex Skills 是模块化的指令包，用来告诉 Codex 如何按你希望的方式完成某类任务。每个 skill 通常放在独立文件夹中，核心文件是 `SKILL.md`，其中包含 frontmatter metadata，例如 `name` 和 `description`，以及具体执行步骤。Codex 会先读取 metadata 判断是否触发，真正需要时再加载正文，从而节省上下文。

## Skills

### 开发与代码工具

- [brooks-lint](https://github.com/hyhmrright/brooks-lint) - 基于六本经典工程书籍的 AI 代码评审，带腐化风险诊断、书籍引用、严重级别和四种分析模式。安装：`python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo hyhmrright/brooks-lint --path skills/brooks-lint --name brooks-lint`
- [bringyour-migration-auditor](https://github.com/unitedideas/bringyour-mcp/tree/main/skills/bringyour-migration-auditor) - 审计 Claude Code 到 Codex harness 的迁移，包括 AGENTS.md/CLAUDE.md 作用域、hooks、MCP 配置、skills、secrets 和验证说明。安装：`python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo unitedideas/bringyour-mcp --path skills/bringyour-migration-auditor --name bringyour-migration-auditor`
- [codebase-migrate/](./codebase-migrate/) - 以可评审批次执行大型代码库迁移和多文件重构，并配合 CI 验证。
- [codebase-recon](https://github.com/yujiachen-y/codebase-recon-skill) - 通过 git 历史理解代码库，先定位热点、缺陷高发区、关键维护者和高风险文件。安装：`python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo yujiachen-y/codebase-recon-skill --path skills/codebase-recon --name codebase-recon`
- [create-plan/](./create-plan/) - 为编码任务快速生成简洁执行计划。
- [deploy-pipeline/](./deploy-pipeline/) - 面向 Stripe、Supabase、Vercel 的端到端发布流水线，包含验证和回滚。
- [Emdash Skills](https://github.com/megabytespace/claude-skills) - 14 类自主产品构建 OS，覆盖 CF Workers、Hono、Angular、D1、Stripe，包含参考文档、agents 和 Codex 原生 `.agents/skills/` 支持。
- [gh-address-comments/](./gh-address-comments/) - 使用 `gh` 处理当前分支对应 GitHub PR 的 review 或 issue 评论。
- [gh-fix-ci/](./gh-fix-ci/) - 检查失败的 GitHub Actions，汇总失败原因并提出修复方案。
- [mcp-builder/](./mcp-builder/) - 按最佳实践和评估 harness 构建、评估 MCP server。
- [pr-review-ci-fix/](./pr-review-ci-fix/) - 通过 Composio CLI 自动做 GitHub/GitLab PR review 和 CI 修复循环。
- [sentry-triage/](./sentry-triage/) - 将 Sentry 堆栈帧映射到本地源码，诊断 issue，无需复制粘贴堆栈。
- [webapp-testing/](./webapp-testing/) - 运行有针对性的 Web 应用测试并汇总结果。
- [AuraKit](https://github.com/smorky850612/Aurakit) - 一体化 skill 框架，包含多种模式、子 agent、安全层、生命周期 hooks 和 token 节省策略。安装：`npx @smorky85/aurakit`
- [Vibe-Skills](https://github.com/foryourhealth111-pixel/Vibe-Skills) - 受治理的 Codex skill harness，支持需求冻结、计划审批、执行、验证证据和跨会话记忆。
- [polywave](https://github.com/blackwell-systems/polywave-codex) - 并行 agent 协作与结构化合并安全机制，Scout 拆解任务，Wave agents 在隔离 worktree 中实现。

### 效率与协作

- [connect/](./connect/) - 通过 Composio CLI 连接 1000+ 应用，让 Codex 执行 Slack、GitHub、Notion 等真实动作。
- [connect-apps/](./connect-apps/) - 为 Claude/Codex 连接 Composio CLI 应用，并从 shell 触发应用工作流。
- [issue-triage/](./issue-triage/) - 从终端分诊 Linear 或 Jira backlog，并执行 bug sweep。
- [linear/](./linear/) - 管理 Linear 中的 issue、项目和团队工作流。
- [meeting-insights-analyzer/](./meeting-insights-analyzer/) - 分析会议文本，提取主题、风险、沟通模式和后续动作。
- [meeting-notes-and-actions/](./meeting-notes-and-actions/) - 把会议转写或粗略笔记整理成摘要、决策和带负责人的行动项。
- [internal-comms/](./internal-comms/) - 撰写内部公告、状态更新、FAQ、事故报告和利益相关方沟通材料。
- [invoice-organizer/](./invoice-organizer/) - 规范化并提取发票数据，用于跟踪、报表和税务准备。
- [notion-knowledge-capture/](./notion-knowledge-capture/) - 把聊天或笔记转成结构化 Notion 页面，并做好链接。
- [notion-meeting-intelligence/](./notion-meeting-intelligence/) - 结合 Notion 上下文和 Codex research 准备会议材料。
- [notion-research-documentation/](./notion-research-documentation/) - 汇总多个 Notion 来源，生成 brief、对比或带引用报告。
- [notion-spec-to-implementation/](./notion-spec-to-implementation/) - 把 Notion 规格文档转成实现计划、任务和进度跟踪。
- [support-ticket-triage/](./support-ticket-triage/) - 对客服 ticket 分类、定优先级、提取下一步并起草回复。
- [file-organizer/](./file-organizer/) - 整理、重命名和清理文件，让工作区保持有序。
- [paperjsx/](./paperjsx/) - 从结构化 JSON 生成 PPTX、DOCX、XLSX 和 PDF 报告/图表/发票，可通过 `@paperjsx/mcp-server` 本地运行。
- [skill-share/](./skill-share/) - 在团队间分享 skills 和可复用指令。

### 沟通与写作

- [codex-sms-verification](https://github.com/virtualsms-io/codex-sms-verification) - 外部仓库：通过 VirtualSMS MCP 为 AI agent 提供真实 SIM 短信验证，支持托管和本地 stdio transports。
- [email-draft-polish/](./email-draft-polish/) - 根据目标语气、长度和受众起草、改写或压缩邮件。
- [changelog-generator/](./changelog-generator/) - 根据 commits 或摘要生成清晰的 changelog。
- [content-research-writer/](./content-research-writer/) - 做资料研究并撰写带来源引用的内容。
- [diasporic-intelligence](https://github.com/MinistaJazz/diasporic-intelligence) - 外部仓库：面向同意治理、署名、来源、撤回和非冒充边界的 source-credit skill。
- [novel-writing](https://github.com/wgwtest/novel-writing) - 外部仓库：用于小说规划、章节起草、场景续写和修订的 Codex skill。
- [tailored-resume-generator/](./tailored-resume-generator/) - 根据岗位描述定制简历，突出相关经验、技能和量化成果。
- [unslop](https://github.com/MohamedAbdallah-14/unslop) - 外部仓库：CLI 和 MCP server，用于去除常见 AI 写作痕迹，支持多种强度和 lint-only 审计模式。

### 数据与分析

- [spreadsheet-formula-helper/](./spreadsheet-formula-helper/) - 编写和调试 Excel/Google Sheets 公式、透视表和数组公式。
- [competitive-ads-extractor/](./competitive-ads-extractor/) - 分析竞品广告，提取可复用的信息、问题和创意方向。
- [datadog-logs/](./datadog-logs/) - 通过 Composio CLI 从 shell 过滤 Datadog logs，并输出 JSON 友好结果。
- [developer-growth-analysis/](./developer-growth-analysis/) - 分析 Codex 聊天历史，识别编码习惯、成长缺口并生成个性化报告。
- [lead-research-assistant/](./lead-research-assistant/) - 研究潜在客户，补充 firmographic 信息和联系策略。
- [domain-name-brainstormer/](./domain-name-brainstormer/) - 根据条件生成并检查域名候选。
- [raffle-winner-picker/](./raffle-winner-picker/) - 用可审计日志随机抽取中奖者。
- [langsmith-fetch/](./langsmith-fetch/) - 拉取 LangSmith 项目/测试数据用于分析和调试。
- [helium-mcp/](./helium-mcp/) - 通过 MCP 搜索实时新闻、市场数据、期权定价和多角度新闻综合。

### 元工具与实用工具

- [brand-guidelines/](./brand-guidelines/) - 将 OpenAI/Codex 品牌色和排版应用到产物。
- [agent-deep-links/](./agent-deep-links/) - 构建并验证 Codex、Cursor、VS Code 深链接，兼顾 Slack 安全格式和 fallback。
- [canvas-design/](./canvas-design/) - 生成结构化 canvas 布局和静态设计产物。
- [image-enhancer/](./image-enhancer/) - 按预设提升图片清晰度、锐度和分辨率。
- [slack-gif-creator/](./slack-gif-creator/) - 生成适合 Slack 的 GIF，包含字幕和样式。
- [theme-factory/](./theme-factory/) - 创建可复用的主题 token、配色和字体方案。
- [video-downloader/](./video-downloader/) - 下载并准备离线查看的视频。
- [template-skill/](./template-skill/) - 构建新 skill 的入门模板。
- [skill-installer/](./skill-installer/) - 从精选列表或 GitHub 路径安装 skill 的辅助脚本。
- [skill-creator/](./skill-creator/) - 编写高质量 Codex skill 的指导。

## 在 Codex 中使用 Skills

- Skills 默认放在 `$CODEX_HOME/skills`，通常是 `~/.codex/skills`。
- 每个子目录需要一个带 `name` 和 `description` frontmatter 的 `SKILL.md`。
- 安装或更新后重启 Codex。
- 在会话中自然描述任务即可触发匹配 skill，也可以直接提到 skill 名称。
- 可用 `ls ~/.codex/skills` 查看已安装 skills，并用 `head ~/.codex/skills/<skill>/SKILL.md` 检查 metadata。

## 创建 Skills

推荐结构：

```text
skill-name/
|-- SKILL.md          # 必需：说明 + YAML frontmatter
|-- scripts/          # 可选：可重复执行的脚本
|-- references/       # 可选：只在需要时加载的长文档
`-- assets/           # 可选：模板或输出所需资源
```

基础模板：

```markdown
---
name: my-skill-name
description: What the skill does and when Codex should use it.
---

# My Skill Name

Clear instructions and steps for Codex to execute the task.
```

最佳实践：

- `description` 要清楚覆盖触发场景，正文专注于执行步骤。
- 使用 progressive disclosure：把详细参考资料放进 `references/`，只在 `SKILL.md` 中说明何时加载。
- 对可重复、确定性的操作提供脚本，并说明 Codex 什么时候应该运行。
- skill 文件夹内尽量避免额外 README/changelog，减少上下文噪声。

## 贡献

欢迎 PR。请优先添加真实、可复用的 skill，保持描述精准，并包含必要脚本或参考资料。新增 skill 时，请确保 `description` 能明确说明触发条件。

中文化贡献建议：

- 保留原 skill 名称和路径，避免破坏安装命令。
- 优先翻译 README 索引和 `SKILL.md` 的 `description`。
- 不确定含义时保留英文术语，并补充中文解释。
- 不要删除原作者署名、外部链接或上游来源信息。

## 社区与资源

- [源仓库](https://github.com/ComposioHQ/awesome-codex-skills)
- [Composio Discord](https://discord.com/invite/composio)
- [Composio X](https://twitter.com/composio)
- [Top Codex Skills](https://composio.dev/content/top-codex-skills)
- 问题反馈：[support@composio.dev](mailto:support@composio.dev)

## 同步策略

本仓库配置了 GitHub Actions 自动同步：

- 每天定时拉取源仓库 `ComposioHQ/awesome-codex-skills` 的 `master` 分支。
- 上游更新会进入 `sync-upstream` 分支，并自动创建或更新 PR。
- 合并冲突默认优先保留中文仓库现有内容，尤其是中文 README。
- 合并 PR 前建议人工检查新增 skills、上游说明变化和版权/许可证变化。

---

<p align="center">
  <b>面向中文用户的 Codex Skills 整理版</b>
</p>
