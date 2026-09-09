# Visual Learning OS

A teaching-first Claude Code **skill**: plain language before jargon,
auto-generated visuals, explicit trade-offs, and a **Work Recap & Feedback
Mode** that reviews your actual changes (via `git diff`) in plain language,
grounded in specific file/line evidence rather than generic praise.

**Manual, and honest about being manual.** This used to be a Claude Code
*output style* — a full system-prompt replacement that stays on for the whole
session until you switch it back yourself. It's a skill now so it can be
invoked per task instead of running your whole session.

One thing the rebuild does **not** claim: it does not auto-detect when your
topic has ended and silently switch itself off. There's no reliable signal
for that. Instead:

- It applies only when you run `/visual-learning-os` (or ask for it by name).
- Once invoked, it stays active for that task or topic — including follow-ups.
- It ends when you say to stop, you clearly change topic, or Claude judges the
  topic finished — and when Claude does that, the reply's first line is
  `(back to default responses)`, so the switch is always visible.

## Files

All under `.claude/skills/visual-learning-os/`:

- `SKILL.md` — the skill: when it applies, scope/exit rules, core principle,
  response structure, teaching mode, Work Recap & Feedback Mode, Existing
  System First, Knowledge Graph First, grounding rules, red flags, golden
  rules.
- `reference/domain-modes.md` — domain-specific behavior (architecture,
  framework/language learning, types, UI/design system, API layer,
  backend/database, native wrappers, testing, component docs, founder mode,
  decision support, code explanation, debugging). Read on demand.
- `reference/visual-style-guide.md` — visual design system, formats, quality
  checklist, print-ready guide mode, render validation. Read on demand.
- `reference/delivery.md` — first-run output-language handling, the
  conditional **Sources** line, the conditional **PDF** offer. Read on demand.
- `stack-profile.template.md` — a blank template. Copy it into each project
  as `stack-profile.md` and fill it in there. **Never** copy a filled-in
  `stack-profile.md` between projects.

## Why project-scoped, not global

`SKILL.md` and `reference/` are identical everywhere and safe to re-pull from
a personal template. Only `stack-profile.md` is project-specific — each
project describes its own stack, so working on two projects in a day never
mixes them up.

## One-time setup: personal template stash

Paste into Claude Code once, on any machine:

```
Set up the "visual-learning-os" skill as a project-scoped skill —
never at the user/global level, so different projects never share
or mix stack profiles.

1. Fetch these files from angelo5003/visual-learning-os, branch main,
   path .claude/skills/visual-learning-os/, into a personal template
   stash at ~/.claude/templates/visual-learning-os/:
   - SKILL.md
   - reference/domain-modes.md
   - reference/visual-style-guide.md
   - reference/delivery.md
   - stack-profile.template.md
   This stash is a source to copy from only.

2. Confirm the files landed at the right paths and show me the listing.
```

## Per-project setup — repeat in each project

```
Install the visual-learning-os skill for this project from my template
stash at ~/.claude/templates/visual-learning-os/:

1. Copy SKILL.md and reference/ from the stash into
   ./.claude/skills/visual-learning-os/ in this project, unchanged.
2. Copy stack-profile.template.md from the stash to
   ./.claude/skills/visual-learning-os/stack-profile.md in this project,
   then fill it in by inspecting this project's package.json /
   requirements.txt / etc. and its own CLAUDE.md / AGENTS.md if either
   exists.
3. Show me the files you created and the filled-in profile.
```

No `settings.json` edit, no activation step. Installing the files never
changes how the project behaves — only invoking `/visual-learning-os` does,
and only for that task.

## Using it

```
/visual-learning-os
```

Type that whenever you want it for the task at hand. It confirms it's active
(`Using Visual Learning OS for this.`), helps with that task, and marks the
switch back with `(back to default responses)` when the topic is done.

## How often do I run this?

- **Stash setup** → once per laptop (again only to pull an improved version).
- **Per-project file setup** → once per project.
- **Invoking `/visual-learning-os`** → every time you want it for a task.
  That's the point — it's a deliberate per-task choice, not a mode that
  stays on.

## Keeping projects up to date

When you improve `SKILL.md` or a reference file, re-pull into your template
stash, then re-copy `SKILL.md` and `reference/` into each project's
`.claude/skills/visual-learning-os/`. **Never** copy `stack-profile.md` (the
filled-in one) in either direction — only the blank
`stack-profile.template.md` travels between projects.

## Rules baked into the skill

- **Never installs a new MCP server, plugin, or skill on its own
  initiative** — it uses only what's already in your environment, and names
  what would help so you can decide.
- **Grounds Work Recap & Feedback Mode in the real diff**, never memory of
  the conversation — feedback always cites a specific file/line.
- **Understanding before terminology** — no jargon before a plain-language
  explanation whenever the skill is active.
