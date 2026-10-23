> **Lithium-battery edition:** This public repository provides `lithium-battery-*` skills. Install and update from `charlie-sys/lithium-battery-research-skills`; original-project links provide attribution and historical material.

Current repository: [charlie-sys/lithium-battery-research-skills](https://github.com/charlie-sys/lithium-battery-research-skills). Adapted from [Yuan1z0825/nature-skills](https://github.com/Yuan1z0825/nature-skills), with the original license and attribution retained.

Invoke a specific skill with `$lithium-battery-polishing` (translate or polish existing prose), `$lithium-battery-writing` (draft sections), `$lithium-battery-reviewer` (mock peer review), `$lithium-battery-citation` (citation support), or `$lithium-battery-figure` (scientific figures). `$lithium-battery-paper-trans` retains its English-PDF-to-Chinese-PDF workflow; use `$lithium-battery-polishing` for Chinese-to-English manuscript translation. `lithium-battery-shared` is an internal support package, not a standalone workflow.

For new papers, corpus updates, and team maintenance, start with [7.4 Collaborative Corpus and Skill Maintenance](#74-collaborative-corpus-and-skill-maintenance). That workflow uses this repository's URL.

<div align="center">
  <p>
    <img src="assets/readme-banner-en.png" alt="Nature Skills: Reusable Research Skills for AI Scholars" width="100%">
  </p>
  <p>
    <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/license-Apache--2.0-2ea44f"></a>
    <a href="#5-installation"><img alt="Install" src="https://img.shields.io/badge/install-Claude%20Code%20%7C%20Codex%20%7C%20OpenClaw%20%7C%20OpenCode%20%7C%20Hermes-111827"></a>
    <a href="#6-skill-index"><img alt="Skills" src="https://img.shields.io/badge/skills-22-0ea5e9"></a>
    <a href="README.md"><img alt="Language" src="https://img.shields.io/badge/language-English%20%7C%20中文-1f6feb"></a>
  </p>
  <p>
    <a href="https://yuan1z0825.github.io/nature-skills/">Website</a>
    · <a href="#5-installation">Install</a>
    · <a href="#4-quick-start">Quick Start</a>
    · <a href="#6-skill-index">Skill Index</a>
    · <a href="docs/open-source-agent-frameworks_EN.md">Other Install</a>
    · <a href="#7-contribution-and-development">Contributing</a>
    · <a href="README.md">中文</a>
  </p>
</div>

---

> **Local domain-specific copy:** `nature-skills-lithium-battery-v1` is based on the original Nature Skills and adds conditional lithium-ion battery state-estimation guidance to all 23 skill directories. The full corpus-derived writing guide is in [`lithium-battery-shared`](skills/lithium-battery-shared/core/battery-state-estimation-writing-style.md). This is not an official release of the original project or any target journal; unrelated tasks retain the original skill workflows.

`nature-skills` collects reusable research skills for AI scholars worldwide, with an emphasis on real problem solving, verifiable workflows, and research outputs that can be used directly.

## Table of Contents

- [1. Project Founder and Operations](#1-project-founder-and-operations)
  - [1.1 Original Project](#11-original-project)
  - [1.2 Current Edition Maintainer](#12-current-edition-maintainer)
- [2. Nature Skills Core Developers](#2-nature-skills-core-developers)
- [3. Project Philosophy and Community](#3-project-philosophy-and-community)
- [4. Quick Start](#4-quick-start)
- [5. Installation](#5-installation)
  - [5.1 `npx skills` Installation](#51-npx-skills-installation)
  - [5.2 Claude Code Installation](#52-claude-code-installation)
  - [5.3 Codex Installation](#53-codex-installation)
  - [5.4 Chatbox Installation and Usage](#54-chatbox-installation-and-usage)
  - [5.5 Other Agent Scenarios](#55-other-agent-scenarios)
- [6. Skill Index](#6-skill-index)
- [7. Contribution and Development](#7-contribution-and-development)
  - [7.4 Collaborative Corpus and Skill Maintenance](#74-collaborative-corpus-and-skill-maintenance)
- [8. Star History](#8-star-history)

## 1. Project Founder and Operations

### 1.1 Original Project

This edition is adapted from [Nature Skills](https://github.com/Yuan1z0825/nature-skills), initiated by Yizhe Yuan. Its reusable research skills and workflows provide the foundation for this domain adaptation. This repository retains the original license and attribution; the original project's introduction and operational information are available in its repository.

### 1.2 Current Edition Maintainer

[charlie-sys](https://github.com/charlie-sys) maintains the lithium-battery edition in [lithium-battery-research-skills](https://github.com/charlie-sys/lithium-battery-research-skills). Maintenance covers lithium-ion battery state-estimation corpus analysis, domain writing guidance, skill adaptation, releases, and contribution review.

Submit issues and update proposals through this repository's Issues or Pull Requests. The repository is public, and all users can contribute through [Section 7.4](#74-collaborative-corpus-and-skill-maintenance).

## 2. Nature Skills Core Developers

The original project's main developers include Yizhe Yuan, Xin-Rui Ma, and Bin Hu, who contributed the original skill system, core architecture, and research workflows. Consult the [Nature Skills repository](https://github.com/Yuan1z0825/nature-skills) for its contributor information.

Maintenance of this edition builds on that work:

| Maintainer | Role in This Edition | Maintenance Scope | Collaboration |
|---|---|---|---|
| **[charlie-sys](https://github.com/charlie-sys)** | Lithium-battery edition maintainer | Domain corpus and writing guidance, `lithium-battery-*` skill adaptation, repository and CI maintenance, update review, and releases | [Current repository](https://github.com/charlie-sys/lithium-battery-research-skills) |

Subsequent contributions are attributed through PRs and commit history. Add source records, applicable scope, and validation results with new papers, corpus material, or rules.

## 3. Project Philosophy and Community

> **Source attribution:** This section is retained from the [original Nature Skills project](https://github.com/Yuan1z0825/nature-skills). Its philosophy, first-person statements, and community information belong to the original team; “I” and “we” refer to the original author or team. It presents the original project's design background and does not represent the personal views of this lithium-battery edition's maintainer. Consult the original project for supporting evidence and current community information.

### 3.1 Some Personal Views

- Recently, I noticed that the Nature Skills design has drawn attention from
  Google DeepMind and has been referenced by them. They drew on its citation
  system, script ideas, and skill-design philosophy to launch Science Skills. To
  be honest, this makes me pleased: when leading international AI institutions
  begin to draw inspiration from our work, it means original ideas from Chinese
  developers are being seen by the world. This is not a feeling of loss from
  being copied, but a sign of Chinese strength taking root in open source and
  naturally growing outward.
- The focus of our skill design has never been to require every user to fully
  master the whole philosophy. The point is that the philosophy itself can be
  understood and reused by machines. If you want to create a new skill or adapt
  this system to your own field, you can give the Nature Skills GitHub repository
  to Codex and let it learn the design pattern, then help you create or modify a
  skill. This is how ideas become operational rather than remaining oral
  explanations.
- The real value of Nature Skills may not be limited to any individual module.
  It may be that the project has quietly opened a new door: many people realize
  for the first time that Codex or other agents can operate a local computer for
  research. I have been fortunate to witness and accompany many people through
  this shift in research workflow. When they say, "so research can be done this
  way," that break in understanding and liberation of thought matters more to me
  than the skills themselves. This is not merely the success of a tool, but the
  beginning of a new way of thinking spreading among people.
- In practice, almost every useful tool can be distilled into a standardized
  process, and standardized processes can be packaged as reusable skills.

### 3.2 Tutorials and Community

The tutorials, community links, and contact details below come from the original team and refer to its community resources. Use this repository's Issues or Pull Requests to collaborate on the current edition. Consult the original project for the latest availability of these resources.

<table>
  <tr>
    <td align="center">
      <b>Follow Douyin for video tutorials</b><br>
      <img width="300" alt="Douyin tutorials" src="https://github.com/user-attachments/assets/37d4b0b6-3d22-4492-bb01-c0d9bae5a9e0" />
    </td>
    <td align="center">
      <b>Agent Research Community</b><br>
      <img width="300" alt="Agent Research Community" src="https://github.com/user-attachments/assets/28d1886a-69be-46bc-a1cb-777d7510ddab" />
    </td>
    <td align="center">
      <b>Yuan's personal WeChat</b><br>
      <img width="300" alt="personal WeChat" src="https://github.com/user-attachments/assets/88e6b293-bda3-4094-94f9-aff4aa5a8842" />
    </td>
  </tr>
</table>

## 4. Quick Start

This public repository contains **22 callable lithium-ion battery research skills and one shared support package**. After installation, invoke a skill in Codex with `$lithium-battery-<name>`, or in Claude Code with `/lithium-battery-<name>`.

| Task | Example Codex request |
|---|---|
| Chinese-to-English translation / English polishing | `Use $lithium-battery-polishing to revise this SOH draft into academic English. Follow the repository's battery writing guide and preserve meaning, numbers, and evidence limits.` |
| Draft an abstract, introduction, or discussion | `Use $lithium-battery-writing to draft an abstract from these results for [journal]. Mark missing information for the author.` |
| Bilingual paper reading | `Use $lithium-battery-reader to read [absolute paper path] and produce a bilingual Markdown reader with figures, equations, and source locations.` |
| Paper presentation | `Use $lithium-battery-paper2ppt to create a Chinese group-meeting PPT from this paper, retaining key figures and source attribution.` |
| Pre-submission review | `Use $lithium-battery-reviewer to assess this SOH estimation paper's methods, validation scope, and support for its conclusions.` |
| Review responses | `Use $lithium-battery-response to draft point-by-point replies from these comments and completed revisions. Do not claim experiments that were not performed.` |
| Broad literature discovery | `Use $lithium-battery-academic-search to find papers on [topic] and verify their DOIs and sources.` |
| Citations within Nature/CNS journals | `Use $lithium-battery-citation to find Nature/CNS sources supporting these claims and explain the match.` |
| Scientific figures | `Use $lithium-battery-figure to plot these SOC/SOH results with units, baselines, and test conditions.` |

Supply accessible manuscript/data paths, the requested scope, output directory, and target journal if known. Otherwise use clear, accurate domain English; check current journal instructions when a target is specified. `lithium-battery-paper-trans` translates English PDFs into Chinese PDFs; choose `lithium-battery-polishing` for Chinese-to-English manuscript translation. Other skills read `lithium-battery-shared` as a support package.

Start with one paragraph and confirm skill loading, domain guidance, numerical fidelity, and terminology before processing a full manuscript. See [Section 7.4](#74-collaborative-corpus-and-skill-maintenance) to add corpus material.

## 5. Installation

**Source:** [charlie-sys/lithium-battery-research-skills](https://github.com/charlie-sys/lithium-battery-research-skills). Public cloning and downloading require no collaborator invitation. Submit changes through PRs. All commands below install this edition's `lithium-battery-*` skills.

Keep each complete skill directory alongside `lithium-battery-shared`, including `SKILL.md`, `agents/`, `references/`, `static/`, scripts, and assets. All domain skills reference the support package, so include it even for selective installation. Python, R, browsers, MCP, and external services require separate setup.

### 5.1 `npx skills` Installation

This method uses the third-party [Vercel Skills CLI](https://github.com/vercel-labs/skills). Its current instructions require **Node.js 22.20 or later**. Check the [official CLI reference](https://github.com/vercel-labs/skills/blob/main/docs/commands.md) and `npx skills --help` for options.

List available skills, then select the desired skill and support package:

~~~bash
npx skills add charlie-sys/lithium-battery-research-skills --list
npx skills add charlie-sys/lithium-battery-research-skills --agent codex --skill lithium-battery-polishing lithium-battery-shared --global --copy --yes
~~~

Install the full collection:

~~~bash
npx skills add charlie-sys/lithium-battery-research-skills --agent codex --skill '*' --global --copy --yes
~~~

`--global` installs at user scope; omit it for the current project. For Claude Code, replace `--agent codex` with `--agent claude-code`. Inspect the result with `npx skills list --global`.

For remote installations managed by this CLI, run `npx skills check`, then `npx skills update lithium-battery-polishing lithium-battery-shared --global` to update those entries. Refresh manual copies and script-managed installations using the instructions below. Choose one maintenance method for each destination.

### 5.2 Claude Code Installation

The [official Claude Code skill documentation](https://code.claude.com/docs/en/skills) specifies `~/.claude/skills/` for personal skills and `.claude/skills/` for project skills. Use the CLI above, or sync complete directories from this repository.

On macOS/Linux, clone and specify the destination explicitly. Bash, Git, `rsync`, and `diff` are required:

~~~bash
git clone https://github.com/charlie-sys/lithium-battery-research-skills.git
cd lithium-battery-research-skills
bash scripts/update-codex-skills.sh --dest "$HOME/.claude/skills"
bash scripts/update-codex-skills.sh --dest "$HOME/.claude/skills" --check
~~~

Despite its name, the script supports other clients through `--dest`. On Windows, use the PowerShell method below with `.claude/skills` as the destination. Invoke `/lithium-battery-polishing` in Claude Code and confirm availability; refresh or restart according to the client documentation if discovery fails.

To update, run `git pull --ff-only origin main` in this clone, then repeat the sync and verification commands.

### 5.3 Codex Installation

**Choose the destination.** Current [OpenAI skill documentation](https://learn.chatgpt.com/docs/build-skills) lists `~/.agents/skills/` for user skills and `.agents/skills/` for project skills. This project has also been deployed and used under `~/.codex/skills/`, which remains the repository script's default. New-install examples below explicitly target `.agents/skills`. If your Codex already loads this edition from `.codex/skills`, update that actual destination to avoid duplicate names across locations.

**macOS/Linux or Bash with all required utilities**

The script requires Git, Bash, `rsync`, and `diff`. On Windows with Bash but without `rsync`, use the PowerShell method below.

~~~bash
git clone https://github.com/charlie-sys/lithium-battery-research-skills.git
cd lithium-battery-research-skills
bash scripts/update-codex-skills.sh --dest "$HOME/.agents/skills"
bash scripts/update-codex-skills.sh --dest "$HOME/.agents/skills" --check
~~~

The script copies all 23 skill directories and verifies file differences. Re-running sync updates matching directories. Back up independent installation edits or bring them into the repository first. To update:

~~~bash
git pull --ff-only origin main
bash scripts/update-codex-skills.sh --dest "$HOME/.agents/skills"
bash scripts/update-codex-skills.sh --dest "$HOME/.agents/skills" --check
~~~

Add `--prune` to remove obsolete skill directories previously managed by this script. For project scope, supply that project's absolute `.agents/skills` path.

**Windows PowerShell**

Install Git, then clone and copy complete skill directories:

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

Both checks should return `True`. For an existing installation under `.codex/skills`, replace `.agents/skills` in `$skillDest` accordingly. For updates, run `git pull --ff-only origin main` in the clone and repeat the copy and checks. PowerShell copying updates files but does not remove old destination files deleted from the repository.

Alternatively, ask Codex:

~~~text
Install skills from https://github.com/charlie-sys/lithium-battery-research-skills.git.
Confirm the user skill directory this Codex installation actually reads, then install
complete lithium-battery-* directories, including lithium-battery-shared.
Check local edits before updating an existing installation, and verify that the
domain writing guide and supporting references can be read.
~~~

Confirm the skills appear in the selector and try a request from Section 4. Restart Codex if a new skill does not appear. Startup hooks are not required by this installation procedure.

**Runtime dependencies and optional update automation**

Begin with writing or polishing for prose tasks. Configure the relevant skill's runtime when using figures, PDF/PPTX tools, downloads, or search services. For example:

~~~bash
python -m pip install -r skills/lithium-battery-image2ppt/requirements.txt
python -m pip install -r skills/lithium-battery-paper-to-patent/requirements.txt
python -m pip install -r skills/lithium-battery-academic-search/mcp-server/requirements.txt
~~~

Configure required credentials locally or in the runtime environment. Installing skill files does not configure external services, browsers, or MCP.

For update automation, use a **dedicated synchronization clone**:

~~~bash
bash scripts/autoupdate-skills.sh --dest "$HOME/.agents/skills" --force
~~~

Use `--force` for the initial sync; omit it in subsequent scheduled calls to retain the default hourly network throttle. Destination drift is checked on each invocation. Logs default to `~/.local/state/lithium-battery-skills/<destination-id>/autoupdate.log`, adjusted by `XDG_STATE_HOME` or `SKILLS_STATE_DIR`. Configure scheduling for the actual client and operating system, keeping the destination consistent.

### 5.4 Chatbox Installation and Usage

This repository does not provide a dedicated Chatbox installer. If your version supports GitHub skill imports, use `https://github.com/charlie-sys/lithium-battery-research-skills` and select the desired skills plus `lithium-battery-shared`. Consult the installed client's documentation for the exact interface.

Alternatively, clone the repository or download Code → Download ZIP on GitHub, extract it, and import complete skill directories into the client's designated location. Keep the support package alongside the skills and update it with them.

In a session with skill loading, file access, and the necessary tools, request “use `lithium-battery-polishing` on this draft” and inspect the loading record. Configure Python, browsers, or MCP in that client when required by the task.

### 5.5 Other Agent Scenarios

Consult the target agent's official documentation for its skill directory and invocation syntax. Copy or install complete `skills/lithium-battery-*` directories and `lithium-battery-shared` from this repository. Clients supported by Vercel Skills CLI can also use Section 5.1 with the appropriate agent selected.

Custom prompts should point to the actual `skills/<skill-name>/SKILL.md` in this clone and permit access to required shared files. Use this repository as the update source; see Section 7.4 for changes and contributions.

## 6. Skill Index

The current `skills/` directory contains the following triggerable skills.
`skills/lithium-battery-shared/` is shared content and is not counted in the skill index. Click a skill name or the "Details" link to open its dedicated documentation page.

| Skill | Status | Purpose | Example Triggers | Details |
|---|---|---|---|---|
| [`lithium-battery-figure`](skills/lithium-battery-figure/README_EN.md) | Stable | Submission-grade Python or R scientific figure workflow for Nature / high-impact journals, with Results-level multi-panel evidence architecture, a render-time panel-alignment gate, automatic final-PDF text/graphic collision QA, separately noticed third-party figures4papers references, original templates, and OpenRouter GPT Image 2 schematic drafts | "Nature figure", "submission-grade figure", "publication plot", "scientific figure", "figures4papers", "paper schematic", "GPT Image 2" | [Details](skills/lithium-battery-figure/README_EN.md) |
| [`lithium-battery-polishing`](skills/lithium-battery-polishing/README_EN.md) | Stable | Polish, restructure, or translate academic prose into Nature-style English, with manuscript-wide terminology, unit, precision, and claim-drift checks | "Nature style", "polishing", "academic writing", "English manuscript" | [Details](skills/lithium-battery-polishing/README_EN.md) |
| [`lithium-battery-writing`](skills/lithium-battery-writing/README_EN.md) | Draft | Draft Nature-style manuscript sections and rebuild a paper argument | "Nature writing", "write an abstract", "write introduction", "manuscript draft", "paper writing" | [Details](skills/lithium-battery-writing/README_EN.md) |
| [`lithium-battery-reviewer`](skills/lithium-battery-reviewer/README_EN.md) | Draft | Simulate Nature-style reviewer assessment with three mutually blind reports, tiered Major/Minor comments, and manuscript-internal consistency checks | "Nature reviewer", "pre-submission review", "reviewer report", "reviewer-perspective assessment" | [Details](skills/lithium-battery-reviewer/README_EN.md) |
| [`lithium-battery-citation`](skills/lithium-battery-citation/README_EN.md) | Beta | Search support literature strictly within Nature / CNS families and export ENW, RIS, or Zotero RDF | "Nature citation", "CNS citation", "segmented citation", "supporting references", "Zotero RDF" | [Details](skills/lithium-battery-citation/README_EN.md) |
| [`lithium-battery-data`](skills/lithium-battery-data/README_EN.md) | Draft | Prepare Data Availability statements, data repository plans, and FAIR checks | "Data Availability", "data availability", "repository", "FAIR metadata" | [Details](skills/lithium-battery-data/README_EN.md) |
| [`lithium-battery-statistics`](skills/lithium-battery-statistics/README_EN.md) | Draft | Audit, revise, or draft statistical reporting, covering experimental units, replicates, p values, multiple comparisons, effect sizes, confidence intervals, figure statistics, and cross-section numeric consistency | "Nature statistics", "statistical analysis", "p value", "sample size", "replicates", "multiple comparisons", "figure statistics", "statistics review" | [Details](skills/lithium-battery-statistics/README_EN.md) |
| [`lithium-battery-reader`](skills/lithium-battery-reader/README_EN.md) | Beta | Generate full-paper Markdown readers with source anchors, figure-text alignment, rendered equations, and Chinese-English side-by-side translation | "nature reader", "full Markdown", "source-aligned text", "figure-text alignment", "rendered equations", "full translation" | [Details](skills/lithium-battery-reader/README_EN.md) |
| [`lithium-battery-paper-xray`](skills/lithium-battery-paper-xray/README_EN.md) | Beta | Read one paper closely enough to retell the authors' reasoning: the real starting point, load-bearing versus decorative design, formulas grounded in worked examples, and the evidence boundary | "paper x-ray", "close reading", "deep read", "how did the authors get here", "explain this paper" | [Details](skills/lithium-battery-paper-xray/README_EN.md) |
| [`lithium-battery-paper-trans`](skills/lithium-battery-paper-trans/README_EN.md) | Beta | Translate a full English paper PDF or selected pages into a Chinese image-based PDF after page comparison, preserving source sizes; A4 on request | "paper translation", "translate paper PDF", "nature paper trans" | [Details](skills/lithium-battery-paper-trans/README_EN.md) |
| [`lithium-battery-paper-card`](skills/lithium-battery-paper-card/README_EN.md) | Beta | Deep-read one paper into a source-grounded Sections 01–16 Paper Card covering method logic, experiment-to-claim evidence, conclusion boundaries, critical analysis, and testable research ideas | "nature paper card", "deep-read paper", "Paper Card", "evidence chain", "conclusion boundaries" | [Details](skills/lithium-battery-paper-card/README_EN.md) |
| [`lithium-battery-response`](skills/lithium-battery-response/README_EN.md) | Beta | Parse revision emails; create separate mutually blind reviewer responses, cover letters, red-marked manuscripts, LaTeX templates, and revision-package consistency checks | "response to reviewers", "rebuttal letter", "cover letter", "major revision", "revision email", "reviewer-comment response", "LaTeX template" | [Details](skills/lithium-battery-response/README_EN.md) |
| [`lithium-battery-paper2ppt`](skills/lithium-battery-paper2ppt/README_EN.md) | Beta | Generate Chinese PPTX journal-club or paper-presentation decks from research papers | "paper PPT", "journal club", "paper to slides", "paper presentation" | [Details](skills/lithium-battery-paper2ppt/README_EN.md) |
| [`lithium-battery-image2ppt`](skills/lithium-battery-image2ppt/README_EN.md) | Beta | Reconstruct slide images, scanned PDFs, and image-only PPTX files as object-level editable PowerPoint with rendered QA | "image to editable PowerPoint", "reconstruct slide screenshot", "scanned PDF to PPTX", "editable PPT" | [Details](skills/lithium-battery-image2ppt/README_EN.md) |
| [`lithium-battery-paper-to-patent`](skills/lithium-battery-paper-to-patent/README_EN.md) | Beta | Generate evidence-constrained Chinese invention patent drafts and support patent-point mining, prior-art search, and iterative technical disclosure drafting | "paper to patent", "Chinese patent", "paper-to-patent", "claims drafting", "technical disclosure", "patent points" | [Details](skills/lithium-battery-paper-to-patent/README_EN.md) |
| [`lithium-battery-ref-verifier`](skills/lithium-battery-ref-verifier/README_EN.md) | Stable | Cross-check references across multiple sources and flag author, title, year, volume, issue, and page inconsistencies | "verify refs", "check references", "reference verification", "ref check" | [Details](skills/lithium-battery-ref-verifier/README_EN.md) |
| [`lithium-battery-academic-search`](skills/lithium-battery-academic-search/README_EN.md) | Beta | Multi-source literature search, citation verification, strict other-citation audits, article-level citation metric tables, influential citer profiling, and reference management | "search papers", "find articles", "literature search", "literature lookup", "verify DOI", "strict other citation", "article citation table", "influential citer" | [Details](skills/lithium-battery-academic-search/README_EN.md) |
| [`lithium-battery-downloader`](skills/lithium-battery-downloader/README_EN.md) | Beta | Legally obtain academic full text/PDFs through library access, Chrome login state, and open-access routes | "download papers", "library paper download", "CARSI", "Web of Science", "PDF download" | [Details](skills/lithium-battery-downloader/README_EN.md) |
| [`lithium-battery-literature-pipeline`](skills/lithium-battery-literature-pipeline/README_EN.md) | Stable | Automated literature discovery pipeline: multi-source retrieval, six-axis scoring, deep-reading delivery, and local archiving | "literature pipeline", "daily literature", "literature push", "daily literature push", "cron" | [Details](skills/lithium-battery-literature-pipeline/README_EN.md) |
| [`lithium-battery-experiment-log`](skills/lithium-battery-experiment-log/README_EN.md) | Draft | Standardize experiment images, voice, and text into Obsidian experiment logs with YAML frontmatter and archived source materials | "experiment log", "record experiment", "Obsidian vault", "Feishu research group" | [Details](skills/lithium-battery-experiment-log/README_EN.md) |
| [`lithium-battery-proposal-writer`](skills/lithium-battery-proposal-writer/README_EN.md) | Beta | Proposal-first research writing state machine: establish evidence, argument, and section contracts before drafting or reviewing text | "lithium-battery-proposal-writer", "proposal", "opening report", "research plan", "research writing QA" | [Details](skills/lithium-battery-proposal-writer/README_EN.md) |
| [`lithium-battery-social-science`](skills/lithium-battery-social-science/README_EN.md) | Draft | Social-science and adjacent-humanities writing and topic-argumentation workbench: topic development, literature landscape, evidence routes with claim ceiling, novelty audit, feasibility assessment, honest-expression self-check | "social science paper", "topic development", "research question", "literature review", "proposal", "overclaiming" | [Details](skills/lithium-battery-social-science/README_EN.md) |

## 7. Contribution and Development

### 7.1 Shared Design Principles

1. **Prefer primary sources**: rules should be grounded in published Nature
   content, official journal guidance, or explicit local sources rather than
   generic taste.
2. **Make rules explicit**: explain the reason behind each rule instead of
   giving unsupported assertions.
3. **Respect section and task context**: writing, figures, citations, and
   responses depend on the manuscript section and task.
4. **Output first**: every skill should produce something directly usable, such
   as paste-ready text, `.svg`, `.pptx`, `.docx`, or concrete instructions.
5. **Keep skills extensible**: each skill should be self-contained, and adding a
   new skill should not require modifying existing skills.

### 7.2 Repository Layout

```text
skills/
├── lithium-battery-shared/              # keep this when skills reference ../lithium-battery-shared
├── lithium-battery-<topic>/
│   ├── README.md
│   ├── README_EN.md
│   ├── SKILL.md
│   ├── manifest.yaml     # present in router-style skills
│   ├── static/           # present in router-style skills
│   └── references/...
└── lithium-battery-proposal-writer/
    ├── README.md
    ├── README_EN.md
    ├── SKILL.md
    ├── scripts/...
    ├── templates/...
    └── references/...
```

### 7.3 Adding a Skill

When adding a skill to this repository, follow this process.

**1. Create the skill directory**

```text
skills/lithium-battery-<topic>/
```

**2. Add required files**

| File | Required | Purpose |
|---|---:|---|
| `SKILL.md` | Yes | Frontmatter (`name`, `description`) plus rules and workflow loaded by the agent |
| `README.md` | Yes | Human-facing Chinese documentation |
| `README_EN.md` | Yes | English documentation paired with the Chinese details page |
| `references/*.md` | Recommended for complex skills | Modular rule files, API references, design theory, tutorials, chart types, and similar material |

**3. Write the Chinese and English READMEs**

Every new skill must include both `README.md` and `README_EN.md`. The README is a human-facing entry page, not a duplicate of `SKILL.md` and not an installation manual. Its job is to help users decide within 30 seconds whether the skill fits their task, what they need to provide, what it will output, and where its boundaries are.

Basic rules:

- The Chinese and English README files must be one-to-one mirrors: same heading count, same order, and same information points. Do not let the English page become a separate template.
- Start with the skill name, language switch link, and one positioning sentence.
- Use the base structure below by default; add optional sections only when they are genuinely needed.
- Do not repeat repository installation instructions, author bios, changelogs, development history, full file trees, or long internal implementation details inside a single skill README.
- Put complex rules, API parameters, long tutorials, script explanations, and template indexes in `references/`, `static/`, `scripts/`, or `SKILL.md`. Keep only navigational pointers in the README.
- If the skill has visual assets, a small preview table is fine; do not turn the README into a large gallery or long technical manual.

Chinese README base structure:

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

The English README must mirror it as:

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

Optional sections must be inserted in both languages and in the same order. Common optional sections:

| Chinese Section | English Section | Use Case |
|---|---|---|
| `## 工作方式` | `## Workflow` | Explain the core workflow or routing behavior |
| `## 运行和依赖` | `## Runtime and Dependencies` | Scripts, MCP services, API keys, local config, or external dependencies |
| `## 示例预览` | `## Example Preview` | A few figures, screenshots, or visual assets are worth showing |
| `## 内置参考` | `## Built-In References` | Point to `references/`, `assets/`, or demos |
| `## 方法来源` | `## Method Sources` | Writing, review, or analysis rules come from specific sources |
| `## 三种模式` | `## Three Modes` | The skill has clear compose/revise/hybrid-style modes |
| `## 与 ... 的关系` | `## Relationship With ...` | The skill is easy to confuse with another skill and needs a division-of-labor note |

Before submitting, run at least these README checks:

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

**4. Record a usage tutorial**

When submitting a PR, please also record a short usage tutorial explaining what
problem the skill solves, how to trigger it, what inputs it needs, and what
outputs it produces. Add the video, screencast link, or public tutorial URL to
the PR description.

**5. Configure `SKILL.md` frontmatter**

```yaml
---
name: lithium-battery-<topic>
description: >-
  One sentence explaining what the skill does, when it should trigger, primary
  outputs, and core use cases.
---
```

**6. Update the skill index**

After adding a skill, update the [Skill Index](#6-skill-index) table:

```markdown
| [`lithium-battery-<topic>`](skills/lithium-battery-<topic>/README_EN.md) | Draft / Stable | One-sentence purpose | Trigger terms | [Details](skills/lithium-battery-<topic>/README_EN.md) |
```

**7. Set the status label**

| Status | Meaning |
|---|---|
| `Draft` | Rules are defined but not yet tested on real cases |
| `Beta` | Tested on examples, with possible edge-case issues |
| `Stable` | Validated on real academic content and relatively stable |

---

### 7.4 Collaborative Corpus and Skill Maintenance

This section covers updates to existing `lithium-battery-*` skills. The repository is public and anyone can clone and use it. Collaborators with write access may push working branches directly. Other contributors first create a GitHub fork, replace the clone URL below with their fork's URL, and submit a Pull Request (PR) to this repository. Everyone uses their own GitHub account. The preceding tutorial requirement for **new skills** does not apply to ordinary corpus updates.

**1. Create a working branch in this repository**

For a first contribution:

```bash
git clone https://github.com/charlie-sys/lithium-battery-research-skills.git
cd lithium-battery-research-skills
git switch -c corpus/add-soh-papers-20261023
```

For an existing clone, commit or otherwise preserve local edits first:

```bash
git switch main
git pull --ff-only origin main
git switch -c corpus/add-soh-papers-20261023
```

Adapt the branch name to the topic and date. For direct collaboration, `origin` points to this repository. For fork contributions, it points to your fork; use a separate remote to track this repository's latest `main`. Keep the original Nature Skills project's remote distinct if needed. Check actual fetch and push targets with `git remote -v`.

**2. Supply the corpus and record its sources**

Keep lawfully obtained PDFs or text outside the repository, for example in an adjacent `battery-corpus/incoming/` folder. Maintain distilled guidance and source records in Git; commit original documents only after confirming that their licenses permit public redistribution. Review staged files for unpublished manuscripts, personal information, and credentials.

For each batch, create a record such as `skills/lithium-battery-shared/references/corpus-updates/YYYY-MM-DD-topic.md` containing:

- Title, authors, year, journal, DOI/publisher link, version read, and reading date; do not count an existing DOI twice.
- Task and conditions: SOC, SOH, capacity, degradation, or RUL; cell/pack and laboratory/field settings where relevant.
- The expression's function, manuscript section, and PDF page or subsection; paraphrase the finding and write fresh examples.
- Agreement, additions, or conflicts with existing guidance, the applicable scope, and affected skill files.

Distinguish the original 48-paper core corpus from additions. Update totals only after deduplication and actual reading, and check related count statements. Label a single-paper usage as an example; claims such as “common” or “preferred” need evidence across papers. If corpus habits conflict with official requirements, consult the target journal's current author instructions and record the source and verification date.

**3. Update the shared guide and instructions that execute it**

| File or location | When to update |
|---|---|
| [Domain writing guide](skills/lithium-battery-shared/core/battery-state-estimation-writing-style.md) | Add or correct terminology, tense, voice, syntax, results, mechanisms, and validation boundaries; link new source records from its corpus anchors. |
| [Domain overlay](skills/lithium-battery-shared/core/battery-domain-overlay.md) | New guide sections or task scopes change which material other skills should read. |
| Affected skills such as `skills/lithium-battery-writing/` and `skills/lithium-battery-polishing/` | Direct instructions in `static/` or `references/` conflict with the guide, or a task genuinely needs new guidance. |
| `skills/lithium-battery-shared/journal-formats/` | Verified changes to official journal requirements; record the evidence and verification date. |

The repository's domain guide is the maintenance entry point for this edition. A separate workspace file named `battery_state_estimation_writing_style.md` does not synchronize automatically; maintain equivalent rules if retaining it, while preserving usable local PDF links or DOI links in each copy. Installed user-directory copies also do not update when the repository is edited.

Skills read the shared guide through the domain overlay, so ordinary corpus additions usually do not require editing every `SKILL.md`. Link each new reference from the guide or relevant skill and explain when to read it. Preserve scientific meaning and evidence boundaries; do not turn a usage observed in one paper into a universal requirement.

Example Codex request; replace the bracketed inputs:

```text
Use skill-creator to update the current lithium-battery skill repository.
New corpus: [absolute PDF/text paths, or paper DOIs/links].
Focus: [terminology, verbs, subjects, voice, syntax, section tenses, results, or mechanisms].
Read the existing shared guide and new material, record sources and page locations,
distinguish the original core corpus from additions, and incorporate supported
findings into the shared guide. Resolve conflicting instructions in affected skills.
Write fresh examples, preserve scientific meaning and evidence limits, and explain
conflicting evidence and its scope. Run the relevant validation and report changed
files, results, and issues requiring human judgment.
Follow the README branch and PR workflow for pushing and merging.
```

**4. Validate and submit a PR**

Run from the repository root with Python 3.11+ and `PyYAML` installed:

```bash
python scripts/validate-repository.py
python scripts/validate-skill-metadata.py
python scripts/validate-readmes.py
python scripts/validate-skill-index.py
git diff --check
git diff
git status --short
```

Run the relevant tooling tests if scripts or tests changed. Verify behavior using an authorized manuscript excerpt: preserve meaning, numbers, units, and evidence strength, and check that new rules apply only in the intended context. In the PR description, include source records, rule changes, scope, validation results, and unresolved conflicts.

Select the intended files, then commit and push the working branch:

```bash
git add <paths-of-files-changed-for-this-update>
git commit -m "Update battery writing guidance from additional corpus"
git push -u origin corpus/add-soh-papers-20261023
```

Create a PR targeting this repository's `main` branch and ask another collaborator to review it. Wait for the triggered GitHub Actions checks; inspect Details and fix any failed checks before merging. Keep skill names, invocation names, and test expectations aligned, and preserve Git executable permissions when editing `.sh` files.

**5. Refresh each user's installed copy after merging**

Direct collaborators run `git switch main` and `git pull --ff-only origin main` in their clone. Fork contributors first synchronize their `main` with this repository. Back up independent installation edits or bring them into the repository, then follow the sync and verification procedure in [Section 5.3](#53-codex-installation) for the actual installation directory. Claude Code users follow Section 5.2. Invoke the relevant skill and confirm that it reads the updated version.

## 8. Star History

The chart below shows the Star history of the original [Yuan1z0825/nature-skills](https://github.com/Yuan1z0825/nature-skills) project and is retained as original-project material. It does not report the Star count or growth of `charlie-sys/lithium-battery-research-skills`. The image is a historical snapshot stored in this repository; consult the original project for live data.

[![Star History Chart](assets/star-history-20261022T024032Z.svg)](https://star-history.com/#Yuan1z0825/nature-skills&Date)
