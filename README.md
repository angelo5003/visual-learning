# Visual Learning OS v5

A teaching-first Claude Code output style: plain language before jargon,
auto-generated visuals, explicit trade-offs, and a **Work Recap & Feedback
Mode** that summarizes and reviews your actual changes (via `git diff`) in
plain language, grounded in specific file/line evidence rather than
generic praise.

This repo holds only the **stack-agnostic** parts — the core file and its
two reference files. There is no `stack-profile.md` and no
`.claude/settings.json` here, on purpose: this repo is a source to copy
from into each of your projects, never something to activate directly.

## Files

- `.claude/output-styles/visual-learning-os-v5.md` — the core output
  style (Mission, Core Principle, Response Structure, Teaching Mode,
  Work Recap & Feedback Mode, Existing System First, Knowledge Graph
  First, Skills Workflow, Golden Rules).
- `.claude/output-styles/reference/domain-modes.md` — architecture,
  framework/language learning, type-system rules, UI/design-system
  rules, API-layer rules, backend/database rules, native-wrapper rules,
  testing, component docs, founder mode, decision support, code
  explanation, debugging. Read on demand, not held in context for tasks
  that don't need it.
- `.claude/output-styles/reference/visual-style-guide.md` — visual
  design system, preferred visual formats, quality checklist,
  print-ready guide mode, render validation, documentation/guide
  generation. Also read on demand.

## Why project-scoped, not global

Setting this as your Claude Code *user-level* default (`~/.claude/settings.json`)
would work, but every project would then share one `stack-profile.md` —
work on two projects in a day and whichever you touched last silently
overwrites the other's stack info. Copying the style into each project
individually keeps every project's profile fully independent: switching
between projects never mixes or loses anything.

## One-time setup: create your personal template stash

Paste into Claude Code once, on any machine:

```
Set up "Visual Learning OS v5" as a project-scoped output style —
never at the user/global level, so different projects never share
or mix stack profiles.

1. Fetch these files from angelo5003/visual-learning-os, branch
   main, path .claude/output-styles/, into a personal template
   stash at ~/.claude/templates/visual-learning-os-v5/:
   - visual-learning-os-v5.md
   - reference/domain-modes.md
   - reference/visual-style-guide.md
   This stash is a source to copy from only — never reference it
   directly as an active output style, and never put a
   stack-profile.md in it.

2. Confirm the files landed at the right paths and show me the
   directory listing.
```

## Per-project setup — repeat in each project (new or existing)

```
Set up Visual Learning OS v5 for this project from my template stash
at ~/.claude/templates/visual-learning-os-v5/:

1. Copy visual-learning-os-v5.md and reference/ from the stash into
   ./.claude/output-styles/ in this project.
2. Create or merge ./.claude/settings.json in this project with
   { "outputStyle": "Visual Learning OS v5" } — don't touch
   ~/.claude/settings.json.
3. Create ./.claude/output-styles/stack-profile.md for this project
   by inspecting its package.json/requirements.txt/etc. and its own
   CLAUDE.md/AGENTS.md if either exists.
4. Validate the JSON with jq, and show me the final settings.json
   and the filled-in profile.
```

## Is this one-time, or do I run it every time?

**One-time, at two levels — never something you repeat just to use the style.**

- **Stash setup** → once per **laptop**. Do it again later only if you
  want to pull in an improved version of the style.
- **Per-project setup** → once per **project**. After that, opening the
  project tomorrow, next week, or next month just works automatically —
  no prompt needed, nothing to re-run.

You'd only touch a project's setup again to update it after improving
the stash, or if its stack changed enough to need a new profile.

## Sanity check

Ask Claude Code: *"Show me the active output style for this project
and confirm it's Visual Learning OS v5, and show the stack profile you
filled in."*

## Keeping projects up to date

When you improve the core file or a reference file here, re-pull this
repo into your template stash, then re-copy `visual-learning-os-v5.md`
and `reference/` into each project's `.claude/output-styles/`. **Never**
copy `stack-profile.md` in either direction — it's the one file that
stays project-specific and must never be synced or shared between
projects.

## Rules baked into the style itself

- **Never installs a new MCP server, plugin, or skill on its own
  initiative.** It only uses tools already installed in your
  environment; if nothing installed matches what a task needs, it names
  what would help and asks before suggesting an install, falling back
  to official docs in the meantime.
- **Grounds Work Recap & Feedback Mode in real evidence** (the actual
  diff), never in memory of the conversation alone — feedback always
  cites a specific file/line, never generic praise.
- **Understanding comes before terminology** — no jargon before a plain-
  language explanation, in every response.
