> **锂电池领域版本：** 本公开仓库提供 `lithium-battery-*` 技能。安装和更新请使用 `charlie-sys/lithium-battery-research-skills`；原项目链接用于来源署名和历史资料。

当前版本仓库：[charlie-sys/lithium-battery-research-skills](https://github.com/charlie-sys/lithium-battery-research-skills)。本项目改编自 [Yuan1z0825/nature-skills](https://github.com/Yuan1z0825/nature-skills)，保留原项目许可与署名。

在 Codex 中直接指定所需技能，例如：`$lithium-battery-polishing`（已有稿件中译英或润色）、`$lithium-battery-writing`（起草章节）、`$lithium-battery-reviewer`（模拟审稿）、`$lithium-battery-citation`（文献支撑核查）、`$lithium-battery-figure`（论文绘图）。`$lithium-battery-paper-trans` 的原有工作流是英文 PDF 翻译为中文 PDF；中文论文译为英文应选 `$lithium-battery-polishing`。`lithium-battery-shared` 为内部支持包，不单独调用。

新增论文或语料、更新领域写作规则及多人协作，请先阅读 [7.4 锂电池语料与技能的协作维护](#74-锂电池语料与技能的协作维护)。该流程使用本仓库地址。

<div align="center">
  <p>
    <img src="assets/readme-banner-cn.png" alt="Nature Skills：面向全球学者的科研 Skill 库" width="100%">
  </p>
  <p>
    <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/license-Apache--2.0-2ea44f"></a>
    <a href="#5-安装"><img alt="Install" src="https://img.shields.io/badge/install-Claude%20Code%20%7C%20Codex%20%7C%20OpenClaw%20%7C%20OpenCode%20%7C%20Hermes-111827"></a>
    <a href="#6-技能索引"><img alt="Skills" src="https://img.shields.io/badge/skills-22-0ea5e9"></a>
    <a href="README_EN.md"><img alt="Language" src="https://img.shields.io/badge/language-中文%20%7C%20English-1f6feb"></a>
  </p>
  <p>
    <a href="https://yuan1z0825.github.io/nature-skills/">在线网站</a>
    · <a href="#5-安装">立即安装</a>
    · <a href="#4-快速开始">快速开始</a>
    · <a href="#6-技能索引">技能索引</a>
    · <a href="docs/open-source-agent-frameworks.md">其他安装</a>
    · <a href="#7-贡献与开发">贡献方式</a>
    · <a href="README_EN.md">English</a>
  </p>
  <p>
    <b>Nature Skills 网页版：内置 Nature Polishing（论文润色）与 Nature Figure（科研绘图）核心功能，访问地址 <a href="https://natureskills.cn">https://natureskills.cn</a></b>
  </p>
  <a href="https://natureskills.cn">
    <img width="2559" height="1527" alt="Nature Skills 网页版预览" src="https://github.com/user-attachments/assets/d57703ab-7ccb-4652-8810-8af1bb032032" />
  </a>

</div>


---

> **本地领域化副本：** `nature-skills-lithium-battery-v1` 基于原版 Nature Skills，给全部 23 个技能目录加入按任务触发的锂离子电池状态估计指导。完整语料写作指南见 [`lithium-battery-shared` 中的领域参考文件](skills/lithium-battery-shared/core/battery-state-estimation-writing-style.md)。这不是原项目或目标期刊发布的官方版本；非本领域任务仍按原技能工作流处理。

`nature-skills` 面向全球 AI 学者收录可复用科研技能，强调真实问题解决、可验证工作流与可直接使用的科研产物。

## 目录

- [1. 项目发起人与运营信息](#1-项目发起人与运营信息)
  - [1.1 原项目介绍](#11-原项目介绍)
  - [1.2 当前版本维护人](#12-当前版本维护人)
- [2. Skills 主要开发者](#2-skills-主要开发者)
- [3. 项目理念与社区](#3-项目理念与社区)
- [4. 快速开始](#4-快速开始)
- [5. 安装](#5-安装)
  - [5.1 `npx skills` 安装方式](#51-npx-skills-安装方式)
  - [5.2 Claude Code 安装方式](#52-claude-code-安装方式)
  - [5.3 Codex 安装方式](#53-codex-安装方式)
  - [5.4 Chatbox 安装与使用](#54-chatbox-安装与使用)
  - [5.5 其他 Agent 场景](#55-其他-agent-场景)
- [6. 技能索引](#6-技能索引)
- [7. 贡献与开发](#7-贡献与开发)
  - [7.4 锂电池语料与技能的协作维护](#74-锂电池语料与技能的协作维护)
- [8. Star 历史](#8-star-历史)

## 1. 项目发起人与运营信息

### 1.1 原项目介绍

本项目基于袁一哲发起的 [Nature Skills](https://github.com/Yuan1z0825/nature-skills) 改编。原项目提供可复用的科研技能体系和工作流，为本版本的领域适配奠定基础。本仓库保留原项目的许可与署名；原项目的介绍和运营信息可在其仓库查看。

### 1.2 当前版本维护人

当前锂电池版本由 [charlie-sys](https://github.com/charlie-sys) 负责后续维护，维护仓库为 [lithium-battery-research-skills](https://github.com/charlie-sys/lithium-battery-research-skills)。维护工作包括锂离子电池状态估计语料提炼、领域写作指南更新、技能适配、版本发布与协作审核。

本版本的问题反馈和更新建议通过本仓库的 Issues 或 Pull Request 提交。仓库已公开，任何使用者均可按 [7.4 节](#74-锂电池语料与技能的协作维护)参与维护。

## 2. Skills 主要开发者

原项目的主要开发者包括袁一哲、马昕瑞和胡彬，负责原有技能体系、核心架构及相关科研工作流。原项目贡献者信息以 [Nature Skills 仓库](https://github.com/Yuan1z0825/nature-skills)为准。

在此基础上，当前版本的维护分工如下：

| 维护人 | 当前版本角色 | 主要维护内容 | 协作入口 |
|---|---|---|---|
| **[charlie-sys](https://github.com/charlie-sys)** | 锂电池版本维护人 | 领域语料与写作规范维护、`lithium-battery-*` 技能适配、仓库与 CI 维护、更新审核和版本发布 | [当前仓库](https://github.com/charlie-sys/lithium-battery-research-skills) |

后续协作贡献通过 PR 和提交记录追溯；新增论文、语料和规则时，应同时记录来源、适用范围及验证结果。

## 3. 项目理念与社区

> **来源说明：** 本节保留自 [Nature Skills 原项目](https://github.com/Yuan1z0825/nature-skills)，其中的项目理念、第一人称表述及社区信息均属于原项目团队；“我”“我们”指原文作者或原项目团队。本节用于呈现原项目的设计背景，不代表当前锂电池版本维护人的个人观点；相关陈述的依据与最新社区信息请以原项目为准。

### 3.1 自己的一些浅薄观点

- 最近发现，我设计的 Nature Skills 被谷歌 DeepMind 关注并借鉴，他们参考了其中的引用体系、脚本思路以及技能设计哲学，推出了 Science Skills。说实话，这让我挺欣慰的——当国外的顶尖 AI 机构开始从我们的工作中汲取灵感时，说明中国开发者的原创思想正在被世界看见。这不是被复制的失落，而是中国力量在开源土壤里生根后，自然向外生长出的影响力。
- 我们设计 Skills 的重心，从来不是要求每个人都来啃透这套思想，而是这套思想本身就具备被机器理解并复用的能力。你如果想创立一个全新的 Skill，或者把它适配到自己的专属领域，根本不需要从头学起——直接把 Nature Skills 的 GitHub 地址发给 Codex，它就能自动学习其中的设计精髓，帮你完成新 Skill 的创建和修改。这才是思想的真正解放：它不再依赖口口相传，而是通过 AI 直接流淌进每一个需要它的角落。
- Nature Skills 真正的价值，或许并不在于那些具体的技能模块，而在于它悄悄推开了一扇新的大门——它让很多人第一次意识到，原来可以借助 Codex 或智能体来操控本地电脑做科研。我有幸见证并陪伴了许多人完成科研范式的转变。当他们惊叹“原来科研还可以这样去做”的那一刻，这种认知上的破壁和解放，远比 Skills 本身更让我觉得有意义。它不是一个工具的成功，而是一种新的思考方式开始在人群中蔓延。
- 在当下，几乎所有实用的工具都可以被提炼为标准化流程，而标准化流程恰好可以封装成可复用技能。

### 3.2 视频教程与社区

以下教程、社群入口和联系方式来自原项目团队，指向原项目的社区资源；当前版本的维护协作请通过本仓库的 Issues 或 Pull Request 进行。入口是否仍有效，请以原项目最新说明为准。

<table>
  <tr>
    <td align="center">
      <b>视频教程请关注抖音</b><br>
      <img width="300" alt="抖音视频教程" src="https://github.com/user-attachments/assets/37d4b0b6-3d22-4492-bb01-c0d9bae5a9e0" />
    </td>
    <td align="center">
      <b>Agent 科研交流群</b><br>
      <img width="300" alt="Agent 科研交流群" src="https://github.com/user-attachments/assets/28d1886a-69be-46bc-a1cb-777d7510ddab" />
    </td>
    <td align="center">
      <b>添加个人微信请备注来意</b><br>
      <img width="300" alt="添加个人微信请备注来意" src="https://github.com/user-attachments/assets/88e6b293-bda3-4094-94f9-aff4aa5a8842" />
    </td>
  </tr>
</table>

## 4. 快速开始

本仓库是公开的锂离子电池科研技能库，包含 **22 个可调用技能和 1 个共享支持包**。从本仓库安装后，在 Codex 中使用 `$lithium-battery-技能名` 指定任务；在 Claude Code 中使用相应的 `/lithium-battery-技能名`。

| 任务 | Codex 请求示例 |
|---|---|
| 中文论文译为英文 / 英文润色 | `使用 $lithium-battery-polishing，将这段 SOH 论文初稿改写为学术英文。遵循本仓库的电池领域写作指南，保留科学含义、数值及证据边界。` |
| 起草摘要、引言或讨论 | `使用 $lithium-battery-writing，根据已有结果起草摘要。目标期刊为 [期刊名]；缺失信息请标记待补充。` |
| 论文精读与中英文对照 | `使用 $lithium-battery-reader，读取 [论文绝对路径]，生成保留图表、公式和来源位置的中英文对照 Markdown。` |
| 生成文献汇报 PPT | `使用 $lithium-battery-paper2ppt，将这篇论文制作成中文组会汇报 PPT，注明来源并保留关键图件。` |
| 投稿前审查 | `使用 $lithium-battery-reviewer，检查这篇 SOH 估计论文的方法、验证范围和结论依据。` |
| 回复审稿意见 | `使用 $lithium-battery-response，根据审稿意见和已有修订逐点起草回复；不添加未完成的实验。` |
| 广泛检索领域文献 | `使用 $lithium-battery-academic-search，检索 [主题] 的文献，核对 DOI 和来源。` |
| Nature/CNS 范围内补充引用 | `使用 $lithium-battery-citation，为这些论断寻找 Nature/CNS 系列支撑文献，并说明匹配关系。` |
| 论文绘图 | `使用 $lithium-battery-figure，根据这些数据绘制 SOC/SOH 估计结果图，保留单位、基线与测试条件。` |

提供稿件或数据的可访问路径、任务范围、输出目录，以及目标期刊（如已确定）。未指定期刊时，以清晰、准确的领域学术表达为默认风格；指定期刊后再核对其当前作者指南。`lithium-battery-paper-trans` 用于英文 PDF 翻译为中文 PDF；中文论文译为英文请选择 `lithium-battery-polishing`。`lithium-battery-shared` 供其他技能读取，不单独调用。

首次使用先处理一段文字，检查技能是否加载、是否遵循领域指南、数字和术语是否保留，再处理整篇论文。新增论文语料的维护方式见 [7.4 节](#74-锂电池语料与技能的协作维护)。

## 5. 安装

**安装来源：** [charlie-sys/lithium-battery-research-skills](https://github.com/charlie-sys/lithium-battery-research-skills)。公开克隆和下载无需协作邀请；提交修改按 PR 流程进行。本节命令均获取本版本的 `lithium-battery-*` 技能。

安装时保留完整技能目录及同级的 `lithium-battery-shared`，包括 `SKILL.md`、`agents/`、`references/`、`static/`、脚本和资产。所有领域技能均会引用共享支持包，按需安装时也应同时选中它。技能文件与 Python、R、浏览器、MCP 或外部服务配置分别安装。

### 5.1 `npx skills` 安装方式

本方式使用第三方 [Vercel Skills CLI](https://github.com/vercel-labs/skills)。按其当前说明，需要 **Node.js 22.20 或更高版本**；参数以 [CLI 官方文档](https://github.com/vercel-labs/skills/blob/main/docs/commands.md)和 `npx skills --help` 为准。

列出技能，再选择需要的技能和共享包：

~~~bash
npx skills add charlie-sys/lithium-battery-research-skills --list
npx skills add charlie-sys/lithium-battery-research-skills --agent codex --skill lithium-battery-polishing lithium-battery-shared --global --copy --yes
~~~

安装全部技能：

~~~bash
npx skills add charlie-sys/lithium-battery-research-skills --agent codex --skill '*' --global --copy --yes
~~~

`--global` 表示用户级安装；省略时安装到当前项目。Claude Code 用户将 `--agent codex` 改为 `--agent claude-code`。安装后可用 `npx skills list --global` 查看结果。

通过 CLI 从远程仓库安装的技能可用 `npx skills check` 检查更新，再运行 `npx skills update lithium-battery-polishing lithium-battery-shared --global` 更新相应条目。手动复制或仓库脚本管理的安装，按下节方法更新；同一安装目标选择一种维护方式。

### 5.2 Claude Code 安装方式

[Claude Code 官方技能说明](https://code.claude.com/docs/en/skills)使用用户级目录 `~/.claude/skills/` 或项目级 `.claude/skills/`。可用上一节的 CLI，也可将本仓库完整技能目录同步到该位置。

macOS/Linux 下先克隆本仓库，再指定目标目录运行脚本；需要 Bash、Git、`rsync` 和 `diff`：

~~~bash
git clone https://github.com/charlie-sys/lithium-battery-research-skills.git
cd lithium-battery-research-skills
bash scripts/update-codex-skills.sh --dest "$HOME/.claude/skills"
bash scripts/update-codex-skills.sh --dest "$HOME/.claude/skills" --check
~~~

虽然脚本名包含 `codex`，其 `--dest` 参数支持指定其他客户端的技能目录。Windows 手动复制方法见下一节，将目标目录改为 `.claude/skills`。在 Claude Code 中使用 `/lithium-battery-polishing` 等命令，并确认对应技能可见；发现失败时按客户端文档刷新或重启。

更新时在此克隆目录执行 `git pull --ff-only origin main`，然后重新运行上述同步和检查命令。

### 5.3 Codex 安装方式

**选择安装目录。** 当前 [OpenAI 技能文档](https://learn.chatgpt.com/docs/build-skills)列出用户级 `~/.agents/skills/` 和项目级 `.agents/skills/`。本项目此前已在 `~/.codex/skills/` 部署并使用；仓库脚本的默认目标仍是该目录。以下新安装示例显式指定 `.agents/skills`。如果你的 Codex 已从 `.codex/skills` 加载本版本，请继续更新该实际目录，避免在两个位置安装同名技能。

**macOS/Linux 或具备完整依赖的 Bash 环境**

脚本需要 Git、Bash、`rsync` 和 `diff`；只有 Bash 而没有 `rsync` 的 Windows 环境请用后面的 PowerShell 方法。

~~~bash
git clone https://github.com/charlie-sys/lithium-battery-research-skills.git
cd lithium-battery-research-skills
bash scripts/update-codex-skills.sh --dest "$HOME/.agents/skills"
bash scripts/update-codex-skills.sh --dest "$HOME/.agents/skills" --check
~~~

脚本复制本仓库的全部 23 个技能目录，并校验文件差异。再次执行会同步更新同名目录；如安装副本中有独立修改，先备份或整理回仓库。更新命令：

~~~bash
git pull --ff-only origin main
bash scripts/update-codex-skills.sh --dest "$HOME/.agents/skills"
bash scripts/update-codex-skills.sh --dest "$HOME/.agents/skills" --check
~~~

需要清理此脚本曾管理、而仓库已删除的技能时，可在同步命令中加入 `--prune`。如指定项目级目标，使用该项目的绝对 `.agents/skills` 路径。

**Windows PowerShell**

先安装 Git。首次克隆并复制完整技能目录：

~~~powershell
git clone https://github.com/charlie-sys/lithium-battery-research-skills.git
Set-Location lithium-battery-research-skills
$skillDest = Join-Path $env:USERPROFILE '.agents/skills'
New-Item -ItemType Directory -Path $skillDest -Force | Out-Null
Get-ChildItem -LiteralPath './skills' -Directory -Filter 'lithium-battery-*' | ForEach-Object {
    Copy-Item -LiteralPath $_.FullName -Destination $skillDest -Recurse -Force
}
Test-Path -LiteralPath (Join-Path $skillDest 'lithium-battery-polishing/SKILL.md')
Test-Path -LiteralPath (Join-Path $skillDest 'lithium-battery-shared/core/battery-state-estimation-writing-style.md')
~~~

上述两个检查应返回 `True`。现有安装位于 `.codex/skills` 时，将 `$skillDest` 中的 `.agents/skills` 改成 `.codex/skills`。后续在克隆目录执行 `git pull --ff-only origin main`，再执行复制和检查步骤。PowerShell 复制会更新文件，但不会清理目标目录中已从仓库删除的旧文件。

也可向 Codex 提出：

~~~text
请从 https://github.com/charlie-sys/lithium-battery-research-skills.git 安装技能。
先确认当前 Codex 实际使用的用户级技能目录，再安装完整的 lithium-battery-* 目录，
包含 lithium-battery-shared；如已有同名安装，请检查本地修改后更新。
完成后检查领域写作指南及技能引用文件是否可读取。
~~~

安装后在技能列表中确认 `lithium-battery-polishing` 等条目，并用第 4 节的请求验证。若新技能未出现，重启 Codex。本节不要求配置启动钩子。

**运行依赖与可选更新脚本**

只做文字改写时，先使用写作或润色技能；涉及绘图、PDF、PPTX、下载或检索服务时，再按对应技能的 README 配置依赖。例如：

~~~bash
python -m pip install -r skills/lithium-battery-image2ppt/requirements.txt
python -m pip install -r skills/lithium-battery-paper-to-patent/requirements.txt
python -m pip install -r skills/lithium-battery-academic-search/mcp-server/requirements.txt
~~~

所需 API 凭据在本机或运行环境配置。安装指令文件并不代表浏览器、外部服务或 MCP 已可用。

需要自动化更新时，可在**专门用于同步的克隆**中调用：

~~~bash
bash scripts/autoupdate-skills.sh --dest "$HOME/.agents/skills" --force
~~~

首次同步可使用上述 `--force`；后续周期执行时省略它，使用默认最多每小时一次的联网检查。每次仍检查安装漂移。默认日志位于 `~/.local/state/lithium-battery-skills/<目标目录编号>/autoupdate.log`，设置 `XDG_STATE_HOME` 或 `SKILLS_STATE_DIR` 时随之变化。请按实际客户端和操作系统配置调度，并保持目标目录一致。

### 5.4 Chatbox 安装与使用

本仓库未提供专用 Chatbox 安装器。若当前客户端支持 GitHub Skills 导入，使用本仓库地址 `https://github.com/charlie-sys/lithium-battery-research-skills`，选择所需技能和 `lithium-battery-shared`。具体入口以所用 Chatbox 版本为准。

也可克隆仓库，或从 GitHub 的 Code → Download ZIP 下载后解压，再将完整技能目录导入客户端指定位置。保留共享包与各技能的同级关系；更新时同时更新共享包。

在支持技能加载、文件访问和所需工具的会话中请求“使用 `lithium-battery-polishing` 处理以下稿件”，并检查加载记录。需要 Python、浏览器或 MCP 的任务，须在该客户端配置相应能力。

### 5.5 其他 Agent 场景

先按目标 Agent 的官方说明确认技能目录和调用方式，再从本仓库复制或安装所需的完整 `skills/lithium-battery-*` 目录及 `lithium-battery-shared`。支持 Vercel Skills CLI 的客户端也可按第 5.1 节选择目标 Agent。

如通过自定义提示词引用仓库文件，应指向当前克隆中真实的 `skills/<技能名>/SKILL.md`，并允许读取所需的共享文件。更新来源统一使用本仓库；技能修改和贡献见第 7.4 节。

## 6. 技能索引

当前 `skills/` 下包含以下可触发技能；`skills/lithium-battery-shared/` 是共享内容目录，不计入技能索引。点击技能名或“详情页”可以进入每个 skill 的单独说明页面。

| 技能 | 状态 | 用途 | 触发词 | 详情页 |
|-------|--------|---------|-----------------|--------|
| [`lithium-battery-figure`](skills/lithium-battery-figure/README.md) | Stable | 面向 Nature / 高影响力期刊的 Python 或 R 投稿级科研图工作流，包含 Results 级多面板证据架构、渲染时子图对齐门、最终 PDF 自动文字/图形碰撞审计、第三方 figures4papers 参考示例、原创模板和 OpenRouter GPT Image 2 论文示意图草稿 | “Nature figure”, “投稿级图片”, “publication plot”, “scientific figure”, “figures4papers”, “论文示意图”, “GPT Image 2” | [详情](skills/lithium-battery-figure/README.md) |
| [`lithium-battery-polishing`](skills/lithium-battery-polishing/README.md) | Stable | 将学术文本润色、重构或翻译为 Nature 风格英文，并扫描全文术语、单位、数值精度和声称漂移 | “Nature style”, “润色”, “academic writing”, “论文英文” | [详情](skills/lithium-battery-polishing/README.md) |
| [`lithium-battery-writing`](skills/lithium-battery-writing/README.md) | Draft | 起草 Nature 风格手稿章节，并重建论文论证 | “Nature writing”, “写摘要”, “写引言”, “manuscript draft”, “论文写作” | [详情](skills/lithium-battery-writing/README.md) |
| [`lithium-battery-reviewer`](skills/lithium-battery-reviewer/README.md) | Draft | 从审稿人视角模拟 Nature 风格评审，输出三份互盲 reviewer reports、分级 Major/Minor 意见，并检查手稿内部一致性 | “Nature reviewer”, “预投稿评审”, “reviewer report”, “审稿人视角评估” | [详情](skills/lithium-battery-reviewer/README.md) |
| [`lithium-battery-citation`](skills/lithium-battery-citation/README.md) | Beta | 检索严格限定在 Nature / CNS 系列的支撑文献，并导出 ENW、RIS 或 Zotero RDF | “Nature citation”, “CNS citation”, “分段引用”, “支撑文献”, “Zotero RDF” | [详情](skills/lithium-battery-citation/README.md) |
| [`lithium-battery-data`](skills/lithium-battery-data/README.md) | Draft | 准备 Data Availability statement、数据仓储方案和 FAIR 检查 | “Data Availability”, “数据可用性”, “repository”, “FAIR metadata” | [详情](skills/lithium-battery-data/README.md) |
| [`lithium-battery-statistics`](skills/lithium-battery-statistics/README.md) | Draft | 审查、改写或起草统计报告，覆盖实验单位、重复数、p 值、多重比较、效应量、置信区间、图注统计和跨章节数值一致性 | “Nature statistics”, “统计审查”, “statistical analysis”, “p value”, “sample size”, “replicates”, “multiple comparisons”, “图注统计”, “统计分析小节” | [详情](skills/lithium-battery-statistics/README.md) |
| [`lithium-battery-reader`](skills/lithium-battery-reader/README.md) | Beta | 生成带来源锚点、图文对应、公式渲染和中英文对照的全文 Markdown reader | “nature reader”, “全文 Markdown”, “原文对照”, “图文对应”, “公式渲染”, “全文翻译” | [详情](skills/lithium-battery-reader/README.md) |
| [`lithium-battery-paper-xray`](skills/lithium-battery-paper-xray/README.md) | Beta | 把一篇论文读到能复述作者的推理：还原真实的出发点、分清承重设计与装饰、公式落到能手算的例子、核对证据边界 | “精读论文”, “讲透这篇论文”, “作者为什么这么设计”, “这个公式怎么推出来的”, “paper x-ray” | [详情](skills/lithium-battery-paper-xray/README.md) |
| [`lithium-battery-paper-trans`](skills/lithium-battery-paper-trans/README.md) | Beta | 将英文论文 PDF 全文或指定页逐页生图翻译，对照检查后交付保留源页尺寸的中文图片型 PDF；A4 按需指定 | “论文翻译”, “翻译论文 PDF”, “nature paper trans” | [详情](skills/lithium-battery-paper-trans/README.md) |
| [`lithium-battery-paper-card`](skills/lithium-battery-paper-card/README.md) | Beta | 精读单篇论文并生成有来源约束的 01–16 节 Paper Card，覆盖方法逻辑、实验—结论证据链、结论边界、批判性分析和可检验研究想法 | “nature paper card”, “论文精读”, “Paper Card”, “证据链”, “结论边界” | [详情](skills/lithium-battery-paper-card/README.md) |
| [`lithium-battery-response`](skills/lithium-battery-response/README.md) | Beta | 解析返修邮件，为互盲审稿人分别生成独立回复，并提供 cover letter、标红稿、LaTeX 模板和返修包一致性检查 | “response to reviewers”, “rebuttal letter”, “cover letter”, “major revision”, “返修邮件”, “审稿意见回复”, “修回信”, “LaTeX 模板” | [详情](skills/lithium-battery-response/README.md) |
| [`lithium-battery-paper2ppt`](skills/lithium-battery-paper2ppt/README.md) | Beta | 从科研论文生成中文 PPTX 文献汇报 deck | “paper PPT”, “journal club”, “paper to slides”, “论文汇报” | [详情](skills/lithium-battery-paper2ppt/README.md) |
| [`lithium-battery-image2ppt`](skills/lithium-battery-image2ppt/README.md) | Beta | 将幻灯片图片、扫描 PDF 和图片型 PPTX 重建为对象级可编辑 PowerPoint，并执行渲染 QA | “图片转可编辑PPT”, “截图还原PPT”, “扫描PDF转PPTX”, “image to editable PowerPoint” | [详情](skills/lithium-battery-image2ppt/README.md) |
| [`lithium-battery-paper-to-patent`](skills/lithium-battery-paper-to-patent/README.md) | Beta | 从论文、技术报告或项目材料生成有证据约束的中国发明专利草稿，并支持专利点挖掘、查新和技术交底书迭代 | “paper to patent”, “Chinese patent”, “论文转专利”, “权利要求书”, “技术交底书”, “专利点” | [详情](skills/lithium-battery-paper-to-patent/README.md) |
| [`lithium-battery-ref-verifier`](skills/lithium-battery-ref-verifier/README.md) | Stable | 参考文献多源交叉验证：逐字段对比作者/标题/年份/卷期/页码，标记卷年冲突、作者编造、页码偏差等 | “verify refs”, “校验文献”, “check references”, “文献验证”, “ref check” | [详情](skills/lithium-battery-ref-verifier/README.md) |
| [`lithium-battery-academic-search`](skills/lithium-battery-academic-search/README.md) | Beta | 多源文献检索、引用核验、严格他引审计、文章引用指标表、高影响力引用者画像和参考文献管理 | “search papers”, “find articles”, “literature search”, “查文献”, “verify DOI”, “严格他引”, “文章引用表”, “引用我的文章的人有没有大牛” | [详情](skills/lithium-battery-academic-search/README.md) |
| [`lithium-battery-downloader`](skills/lithium-battery-downloader/README.md) | Beta | 通过图书馆资源入口、Chrome 登录态和开放获取路径合法获取学术全文/PDF | “download papers”, “图书馆下载文献”, “CARSI”, “Web of Science”, “PDF 下载” | [详情](skills/lithium-battery-downloader/README.md) |
| [`lithium-battery-literature-pipeline`](skills/lithium-battery-literature-pipeline/README.md) | Stable | 自动化文献发现管线：多源检索、六维评分、精读推送和本地归档 | “literature pipeline”, “每日文献”, “文献推送”, “daily literature push”, “cron” | [详情](skills/lithium-battery-literature-pipeline/README.md) |
| [`lithium-battery-experiment-log`](skills/lithium-battery-experiment-log/README.md) | Draft | 标准化记录实验图片、语音和文字材料，生成带 YAML frontmatter 的 Obsidian 实验日志并归档原始材料 | “实验日志”, “记录实验”, “experiment log”, “Obsidian vault”, “飞书科研群” | [详情](skills/lithium-battery-experiment-log/README.md) |
| [`lithium-battery-proposal-writer`](skills/lithium-battery-proposal-writer/README.md) | Beta | proposal-first 科研写作状态机，先建立证据、论证和章节契约，再起草或审查文本 | “lithium-battery-proposal-writer”, “proposal”, “开题报告”, “研究方案”, “科研写作 QA” | [详情](skills/lithium-battery-proposal-writer/README.md) |
| [`lithium-battery-social-science`](skills/lithium-battery-social-science/README.md) | Draft | 社科及相邻学科学术写作与选题论证工作台：选题构思、文献版图、证据路线与主张上限、新颖性审计、可行性评估、诚实表述自检 | “社科论文”, “选题”, “research question”, “文献综述”, “开题”, “过度断言” | [详情](skills/lithium-battery-social-science/README.md) |

## 7. 贡献与开发

### 7.1 共享设计原则

所有技能都遵守以下原则：

1. **优先使用一手来源**：规则基于已发表 Nature 内容、官方期刊指南或明确的本地来源，而不是泛泛审美偏好。
2. **显式胜过隐式**：每条规则都应说明理由，而不是只给断言。
3. **感知章节与任务上下文**：学术写作、图件、引用和回复都依赖上下文；不同论文部分使用不同逻辑。
4. **输出优先**：每个技能都应返回能直接使用的产物，例如可粘贴文本、`.svg`、`.pptx`、`.docx` 或具体建议。
5. **可扩展**：每个技能自包含在自己的目录中，新增技能不应要求修改既有技能。

### 7.2 仓库目录结构

```text
skills/
├── lithium-battery-shared/              # 当技能引用 ../lithium-battery-shared 时需要保留
├── lithium-battery-<topic>/
│   ├── README.md
│   ├── README_EN.md
│   ├── SKILL.md
│   ├── manifest.yaml     # router-style 技能会包含
│   ├── static/           # router-style 技能会包含
│   └── references/...
└── lithium-battery-proposal-writer/
    ├── README.md
    ├── README_EN.md
    ├── SKILL.md
    ├── scripts/...
    ├── templates/...
    └── references/...
```

### 7.3 新增技能流程

向本仓库添加技能时，请按以下流程：

**1. 创建技能目录**

```text
skills/lithium-battery-<topic>/
```

**2. 添加必需文件**

| 文件 | 是否必需 | 用途 |
|------|----------|------|
| `SKILL.md` | 必需 | frontmatter（`name`、`description`）+ 规则 + 工作流；触发后由 agent 加载 |
| `README.md` | 必需 | 面向人的中文说明文档 |
| `README_EN.md` | 必需 | 与中文详情页配套的英文说明文档 |
| `references/*.md` | 复杂技能推荐 | 模块化规则文件，例如 API、设计理论、教程、图表类型等 |

**3. 编写中英文 README**

每个新增技能都必须同时提供 `README.md` 和 `README_EN.md`。README 是面向人的技能入口页，不是 `SKILL.md` 的重复版，也不是安装手册。它的目标是让用户在 30 秒内判断：这个 skill 能不能解决我的问题、我要给它什么、它会产出什么、边界在哪里。

基本规则：

- 中文 README 和英文 README 必须一一镜像：标题数量一致、顺序一致、信息点一致；英文页不要写成另一套独立模板。
- 顶部固定为技能名、语言切换链接和一句定位说明。
- 默认使用下面的基础结构；只有确实需要时才插入可选章节。
- 不要在单个 skill README 中重复仓库安装教程、作者信息、变更日志、开发过程、完整文件树或大段内部实现细节。
- 复杂规则、API 参数、长教程、脚本说明和模板索引应放进 `references/`、`static/`、`scripts/` 或 `SKILL.md`，README 只保留路标。
- 如果技能有视觉资产，可以放一个小型预览表；不要把 README 变成大型图库或长篇技术手册。

中文 README 基础结构：

```markdown
# `lithium-battery-<topic>` 技能

[English](README_EN.md)

一句话说明这个技能的定位、主要任务和使用边界。

## 适合用它做什么
## 典型请求
## 你需要提供
## 产出
## 边界
## 相关技能
```

英文 README 必须对应为：

```markdown
# `lithium-battery-<topic>` Skill

[中文说明](README.md)

One sentence describing the skill's role, main task, and usage boundary.

## What To Use It For
## Typical Requests
## What You Need To Provide
## Outputs
## Boundaries
## Related Skills
```

可选章节必须中英文同步插入，并保持相同顺序。常见可选章节包括：

| 中文章节 | 英文章节 | 使用场景 |
|----------|----------|----------|
| `## 工作方式` | `## Workflow` | 需要解释核心流程或路由方式 |
| `## 运行和依赖` | `## Runtime and Dependencies` | 有脚本、MCP、API key、本地配置或外部依赖 |
| `## 示例预览` | `## Example Preview` | 有少量图件、截图或可视化资产值得展示 |
| `## 内置参考` | `## Built-In References` | 需要指向 `references/`、`assets/` 或 demo |
| `## 方法来源` | `## Method Sources` | 写作、审查或分析规则来自特定来源 |
| `## 三种模式` | `## Three Modes` | 技能有清晰的 compose/revise/hybrid 等模式 |
| `## 与 ... 的关系` | `## Relationship With ...` | 容易和另一个技能混淆，需要说明分工 |

提交前至少做这些 README 检查：

```bash
python scripts/validate-readmes.py
git diff --check
for d in skills/lithium-battery-*; do
  [ -f "$d/README.md" ] && [ -f "$d/README_EN.md" ] || continue
  rg -q '^\[English\]\(README_EN\.md\)$' "$d/README.md"
  rg -q '^\[中文说明\]\(README\.md\)$' "$d/README_EN.md"
  test "$(rg -c '^## ' "$d/README.md")" = "$(rg -c '^## ' "$d/README_EN.md")"
done
```

**4. 录制使用教程**

提交 PR 时，请同时录制一个简短的使用教程，说明这个 skill 解决什么问题、如何触发、需要什么输入，以及会产出什么结果。可以在 PR 描述中附上视频、录屏链接或可公开访问的教程地址。

**5. 配置 `SKILL.md` frontmatter**

```yaml
---
name: lithium-battery-<topic>
description: >-
  用一句话说明这个技能做什么、什么时候触发、主要输出格式和核心使用场景。
---
```

**6. 更新技能索引**

在上方 [技能索引](#6-技能索引) 表格中添加一行：

```markdown
| [`lithium-battery-<topic>`](skills/lithium-battery-<topic>/README.md) | Draft / Stable | 一句话用途 | 触发词 | [详情](skills/lithium-battery-<topic>/README.md) |
```

**7. 设置状态标签**

| 标签 | 含义 |
|-------|------|
| `Draft` | 规则已定义，但尚未在真实案例上测试 |
| `Beta` | 已在示例上测试，仍可能存在边界问题 |
| `Stable` | 已在真实学术内容上验证，规则相对稳定 |

---

### 7.4 锂电池语料与技能的协作维护

本节适用于更新已有 `lithium-battery-*` 技能。本仓库已公开，任何人均可克隆和使用。有写入权限的协作人可直接推送工作分支；其他贡献者先在 GitHub 创建本仓库的 Fork，再将下面的克隆地址替换为自己的 Fork 地址，向本仓库提交 Pull Request（PR）。每人使用自己的 GitHub 账号。上节针对**新增技能**的教程要求不作为普通语料更新的必需步骤。

**1. 从当前仓库建立工作分支**

首次协作：

```bash
git clone https://github.com/charlie-sys/lithium-battery-research-skills.git
cd lithium-battery-research-skills
git switch -c corpus/add-soh-papers-20261023
```

已有克隆时，先提交或妥善保存本地修改，再执行：

```bash
git switch main
git pull --ff-only origin main
git switch -c corpus/add-soh-papers-20261023
```

分支名按主题和日期调整。直接协作时 `origin` 指向本仓库；使用 Fork 时 `origin` 指向自己的 Fork，另设远程地址跟踪本仓库以获取最新 `main`。参考原 Nature Skills 项目时，应另行区分其远程地址。用 `git remote -v` 核对实际拉取与推送目标。

**2. 提供语料并记录来源**

将合法取得的 PDF 或文本放在本地仓库之外，例如相邻的 `battery-corpus/incoming/`。仓库维护提炼规则和来源记录；提交原文前须确认其许可允许公开再分发。检查待提交文件，避免混入未公开稿件、个人信息或凭据。

每批更新建议新增 `skills/lithium-battery-shared/references/corpus-updates/YYYY-MM-DD-topic.md`，记录：

- 论文标题、作者、年份、期刊、DOI/出版商链接、读取版本和日期；已存在的 DOI 不重复计入篇数。
- 任务范围：SOC、SOH、容量、衰退或 RUL，以及电芯/电池包、实验室/现场等条件。
- 提炼的表达功能、所在章节及 PDF 页码或小节位置；以自己的话归纳，例句重新撰写。
- 与原指南一致、补充或冲突的内容，适用范围，以及拟修改的技能文件。

保留“原有 48 篇核心语料”与新增补充语料的区别。只有完成去重和实际阅读后才更新总数，并同步检查相关的篇数说明。单篇用法标记为示例；“常用”“更偏好”等判断应有跨论文证据。语料习惯与官方要求冲突时，核对目标期刊当前作者指南，记录来源与核对日期。

**3. 更新共享指南和实际执行规则**

| 文件或位置 | 何时修改 |
|---|---|
| [领域写作指南](skills/lithium-battery-shared/core/battery-state-estimation-writing-style.md) | 新增或修正术语、时态、语态、句式、结果、机制及验证边界；在语料锚点中关联新来源记录。 |
| [领域路由文件](skills/lithium-battery-shared/core/battery-domain-overlay.md) | 指南新增部分或适用任务改变，需要调整其他技能读取哪些内容时。 |
| `skills/lithium-battery-writing/`、`skills/lithium-battery-polishing/` 等受影响技能 | `static/`、`references/` 中有与新指南冲突的直接指令，或确实需要新增任务规则时。 |
| `skills/lithium-battery-shared/journal-formats/` | 官方期刊要求有已核实变化时，注明依据及核对日期。 |

仓库内的领域写作指南是本版本的维护入口。项目工作目录中另存的 `battery_state_estimation_writing_style.md` 不会自动同步到仓库；如需保留该副本，应同步正文规则，并保留两者各自可用的本地文件链接或 DOI 链接。安装到用户目录的副本也不会因仓库编辑而自动更新。

共享指南由各技能通过领域路由读取，普通语料更新通常无需重复修改全部 `SKILL.md`。新增引用文件应从指南或对应技能链接，并说明何时读取；避免堆放不会被读取的材料。保留科学含义与证据边界，不把某篇论文的表达变成所有任务必须遵守的规则。

可在 Codex 中提供以下请求，并替换方括号内容：

```text
使用 skill-creator 更新当前 lithium-battery 技能仓库。
新增语料：[PDF/文本的绝对路径，或论文 DOI/链接]。
提炼范围：[术语、动词、主语、语态、句式、章节时态、结果或机制表达]。
请阅读原共享指南和新语料，记录来源及页码，区分原有核心语料与新增语料，
仅把有依据的归纳写入共享指南，并修正受影响技能中的冲突指令。
不照抄原句，不添加未经证实的科学内容；有冲突时说明依据和适用范围。
完成相应验证，列出修改文件、验证结果与待人工判断的问题。
推送和合并按 README 的分支与 PR 流程进行。
```

**4. 验证并提交 PR**

在仓库根目录运行以下检查（Python 3.11+，并安装 `PyYAML`）：

```bash
python scripts/validate-repository.py
python scripts/validate-skill-metadata.py
python scripts/validate-readmes.py
python scripts/validate-skill-index.py
git diff --check
git diff
git status --short
```

若修改脚本或测试，还需运行对应工具测试。用一段获准使用的稿件验证实际改写：检查科学含义、数字、单位和证据强度是否保留，以及新规则是否只在适用语境生效。PR 描述写明来源记录、规则变更、适用范围、验证结果及尚未解决的冲突。

明确选择本次要提交的文件，再提交并推送工作分支：

```bash
git add <本次修改的文件路径>
git commit -m "Update battery writing guidance from additional corpus"
git push -u origin corpus/add-soh-papers-20261023
```

在本仓库创建目标为 `main` 的 PR，请另一位协作人复核。等待本次触发的 GitHub Actions 检查完成；出现红叉时查看 Details 并修复失败原因，再合并。后续提交应保持技能名称、调用名称和测试预期一致；修改 `.sh` 文件时保留 Git 可执行权限。

**5. 合并后更新每位使用者的安装副本**

直接协作的使用者先在克隆中执行 `git switch main` 和 `git pull --ff-only origin main`；使用 Fork 时先将自己的 `main` 同步至本仓库最新版本。如安装目录存在独立修改，先备份或将其整理回仓库，再按 [5.3 节](#53-codex-安装方式)的同步和检查步骤更新实际安装目录。Claude Code 用户按第 5.2 节更新。随后调用相应技能，确认读取的是更新版本。

## 8. Star 历史

下图展示的是原项目 [Yuan1z0825/nature-skills](https://github.com/Yuan1z0825/nature-skills) 的 Star 历史，作为原项目资料保留；不代表当前 `charlie-sys/lithium-battery-research-skills` 仓库的 Star 数量或增长情况。该图为仓库内保留的历史快照，实时数据请查看原项目。

[![Star History Chart](assets/star-history-20261022T024032Z.svg)](https://star-history.com/#Yuan1z0825/nature-skills&Date)
