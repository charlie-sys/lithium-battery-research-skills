# OpenClaw / OpenCode / Hermes Integration Guide

The core unit in `nature-skills` is a complete skill directory, not a standalone `SKILL.md` file. For open-source agent frameworks such as OpenClaw, OpenCode, and Hermes, keep a stable local clone of this repository and let the target framework scan or reference complete directories under `skills/`.

## Common Setup

```bash
mkdir -p ~/ai-skills
cd ~/ai-skills
git clone https://github.com/Yuan1z0825/nature-skills.git
```

To update later:

```bash
cd ~/ai-skills/nature-skills
git pull
```

Rules:

1. Keep the complete skill directory, such as `skills/lithium-battery-reader/`; do not copy only `SKILL.md`.
2. Keep sibling shared content in `skills/lithium-battery-shared/` when a skill references it.
3. Skills that use scripts, MCP services, or APIs still require their own dependencies, environment variables, and local credentials.

## OpenClaw

OpenClaw workspace skills usually live at:

```text
~/.openclaw/workspace/skills/<skill>/SKILL.md
```

Use symlinks to point OpenClaw at the stable clone:

```bash
mkdir -p ~/.openclaw/workspace/skills
ln -s ~/ai-skills/nature-skills/skills/lithium-battery-reader ~/.openclaw/workspace/skills/lithium-battery-reader
ln -s ~/ai-skills/nature-skills/skills/lithium-battery-shared ~/.openclaw/workspace/skills/lithium-battery-shared
```

Add more skills by linking more `nature-*` directories:

```bash
ln -s ~/ai-skills/nature-skills/skills/lithium-battery-polishing ~/.openclaw/workspace/skills/lithium-battery-polishing
ln -s ~/ai-skills/nature-skills/skills/lithium-battery-writing ~/.openclaw/workspace/skills/lithium-battery-writing
```

If symlinks are inconvenient, copy the full directories instead:

```bash
cp -R ~/ai-skills/nature-skills/skills/lithium-battery-reader ~/.openclaw/workspace/skills/
cp -R ~/ai-skills/nature-skills/skills/lithium-battery-shared ~/.openclaw/workspace/skills/
```

When using copy-based installation, copy the directories again after repository updates.

## OpenCode

OpenCode can discover skills from project or global `.agents/skills/**/SKILL.md` directories. For global use:

```bash
mkdir -p ~/.agents/skills
ln -s ~/ai-skills/nature-skills/skills/lithium-battery-reader ~/.agents/skills/lithium-battery-reader
ln -s ~/ai-skills/nature-skills/skills/lithium-battery-polishing ~/.agents/skills/lithium-battery-polishing
ln -s ~/ai-skills/nature-skills/skills/lithium-battery-shared ~/.agents/skills/lithium-battery-shared
```

For a single project, place the links under that project's `.agents/skills/`:

```bash
cd /path/to/your/project
mkdir -p .agents/skills
ln -s ~/ai-skills/nature-skills/skills/lithium-battery-reader .agents/skills/lithium-battery-reader
ln -s ~/ai-skills/nature-skills/skills/lithium-battery-shared .agents/skills/lithium-battery-shared
```

Newer OpenCode configs can also declare an additional skills path in `opencode.json` or `opencode.jsonc`:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "skills": ["~/ai-skills/nature-skills/skills"]
}
```

Older OpenCode versions may still use this shape:

```json
{
  "skills": {
    "paths": ["~/ai-skills/nature-skills/skills"]
  }
}
```

After starting OpenCode, ask it to use a skill explicitly:

```text
Use the lithium-battery-reader skill to turn this paper into a Chinese-English Markdown reader.
```

## Hermes

Hermes stores local skills under:

```text
~/.hermes/skills/
```

The recommended approach is to add the `nature-skills` `skills/` directory as an external skill directory in `~/.hermes/config.yaml`:

```yaml
skills:
  external_dirs:
    - ~/ai-skills/nature-skills/skills
```

Hermes can then discover skills such as `lithium-battery-reader`, `lithium-battery-polishing`, and `lithium-battery-writing`, and use them as slash commands:

```text
/lithium-battery-reader Turn this paper into a Chinese-English Markdown reader.
```

If you do not want Hermes to scan the external repository directly, copy selected skills into Hermes' own directory:

```bash
mkdir -p ~/.hermes/skills/research
cp -R ~/ai-skills/nature-skills/skills/lithium-battery-reader ~/.hermes/skills/research/
cp -R ~/ai-skills/nature-skills/skills/lithium-battery-polishing ~/.hermes/skills/research/
cp -R ~/ai-skills/nature-skills/skills/lithium-battery-shared ~/.hermes/skills/research/lithium-battery-shared
```

Note that Hermes external skill directories are not a read-only protection boundary. If the external directory is writable by Hermes and you allow skill edits, Hermes may modify files in place. For shared team directories or upstream clones, keep them read-only or copy selected skills into `~/.hermes/skills/`.

## Suggested Starter Set

You do not need to install every skill at first. A practical starter set is:

| Task | Recommended skill |
| --- | --- |
| Paper reading, translation, figure-text alignment | `lithium-battery-reader` |
| Manuscript polishing and English academic expression | `lithium-battery-polishing` |
| Abstract, introduction, and discussion drafting | `lithium-battery-writing` |
| Pre-submission reviewer simulation | `lithium-battery-reviewer` |
| Revision response, cover letter, reviewer replies | `lithium-battery-response` |
| Scientific figures and manuscript schematics | `lithium-battery-figure` |
| Literature search, strict self-citation audit, citer profiling | `lithium-battery-academic-search` |

To link every `nature-*` skill into one directory:

```bash
mkdir -p ~/.agents/skills
for skill in ~/ai-skills/nature-skills/skills/nature-*; do
  ln -s "$skill" ~/.agents/skills/"$(basename "$skill")"
done
```

This example uses OpenCode's global `.agents/skills` directory. For OpenClaw, replace the target with `~/.openclaw/workspace/skills`; for Hermes, prefer `external_dirs`.
