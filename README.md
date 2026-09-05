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

Turning the style *on* is a separate decision from installing it — see
below. Installing it never changes anything about how a project behaves
by itself; only explicitly running `/output-style` or opting into
automatic mode does.

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

**Default: manual.** This installs the style's files into the project
but does **not** turn it on automatically — you choose when to use it,
per session, with a command. Nothing about how the project runs changes
unless you explicitly turn it on.

```
Set up Visual Learning OS v5 for this project from my template stash
at ~/.claude/templates/visual-learning-os-v5/, for MANUAL use — do
not make it the automatic default yet:

1. Copy visual-learning-os-v5.md and reference/ from the stash into
   ./.claude/output-styles/ in this project.
2. Create ./.claude/output-styles/stack-profile.md for this project
   by inspecting its package.json/requirements.txt/etc. and its own
   CLAUDE.md/AGENTS.md if either exists.
3. Do NOT write outputStyle into ./.claude/settings.json.
4. Show me the files you created.
```

### Turning it on for a session (manual mode)

Once installed, switch to it whenever you want with:

```
/output-style Visual Learning OS v5
```

That only affects your current session. Close Claude Code or start a
new session and it's back to the default style — run the command again
next time you want v5.

### Making it automatic instead (optional, your call)

If you'd rather have it on every session in a project without typing
the command each time, say so explicitly:

```
Make Visual Learning OS v5 the automatic default for this project —
set outputStyle in ./.claude/settings.json to "Visual Learning OS v5".
```

This is the only step that changes what happens without you asking
each time, so it's opt-in on purpose, per project.

## Is this one-time, or do I run it every time?

- **Stash setup** → once per **laptop**. Do it again later only if you
  want to pull in an improved version of the style.
- **Per-project file setup** (copying the files, creating the profile) →
  once per **project**.
- **Turning the style on**, after that one-time setup, depends on which
  mode you chose:
  - **Manual (default):** run `/output-style Visual Learning OS v5`
    each session you want it active.
  - **Automatic (opt-in):** nothing to run — it's on every session in
    that project from then on.

## Sanity check

After manually switching with `/output-style`, ask: *"Confirm the
active output style and show the stack profile you filled in."*
(If you made it automatic, this also confirms it's on without you
having run the command.)

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
