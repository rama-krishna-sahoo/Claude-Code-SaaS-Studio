## Applies to
.agents/**/*
.agents/**/*

# Authoring Conventions for Agents, Skills, Hooks, Rules, and Templates

When authoring or modifying any agent, skill, hook, rule, or template file in this repository, strictly adhere to these conventions:

## 1. Agent Files — `.agents/agents/{name}.md`
```markdown
---
name: {kebab-id}
description: "One-line role + when to use it."
tools: Read, Glob, Grep, Write, Edit, Bash, Task, AskUserQuestion
model: opus | sonnet | haiku
maxTurns: 40
---

{1-2 sentence role statement}

### Responsibilities
- ...

### Operating protocol (ask → present options → user decides → draft → approve)
Follow the studio protocol: never write or change files without presenting options and getting sign-off. Honor the active review intensity (`full` / `lean` / `solo`).

### You should NOT do
- ...

### Coordination
Reports to: {agent}
Delegates to: {agents}
Coordinates with: {agents}
```

## 2. Skill Files — `.agents/skills/{name}/SKILL.md`
```markdown
---
name: {kebab-id}
description: "What it does and when to run it."
argument-hint: "[arg] [--review full|lean|solo]"
user-invocable: true
allowed-tools: Read, Glob, Grep, Write, Edit, Bash, Task, AskUserQuestion
model: sonnet
agent: {primary-agent-name}
---

{One-paragraph purpose.}

## Phases
1. **{Phase}** — {what happens, what gate/approval}

## Output
{What artifact/files this produces and where.}
```

## 3. Hook Files — `.agents/hooks/{name}.sh`
POSIX-compatible `#!/usr/bin/env bash`, `set -euo pipefail` where safe, exit non-zero to block. Must pass `bash -n`.

## 4. Rule Files — `.agents/rules/{name}.md`
A `## Applies to` glob line + a bulleted list of MUST/SHOULD standards.

## 5. Template Files — `.agents/templates/{name}.md`
A headed Markdown skeleton. Use `#`/`##` headings for each section a contributor fills in, with `<...>` angle-bracket placeholders marking fill-ins.
