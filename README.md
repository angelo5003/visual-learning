# Visual Learning OS

A teaching-first Claude Code **skill**: plain language before jargon,
auto-generated visuals, explicit trade-offs, and a **Work Recap &
Feedback Mode** that summarizes and reviews your actual changes (via
`git diff`) in plain language, grounded in specific file/line evidence
rather than generic praise.

**Manual only, on purpose.** This used to be a Claude Code *output
style* (a full system-prompt replacement that, once switched on, stays
on for the whole session until you switch it back yourself). It's now a
**skill** instead, specifically so it can behave the way you'd actually
want a teaching mode to behave: invoked on request, scoped to the task
you invoked it for, and handed back to normal default behavior once
that task is done — without you having to remember to switch it off.

## Why a skill, not an output style

| | Output style (what this was) | Skill (what this is now) |
|---|---|---|
| Replaces the system prompt | Yes, entirely | No — supplements default behavior |
| How it turns on | You type `/output-style ...` | You type `/visual-learning-os`, or Claude asks first if it looks like a good fit |
| How it turns off | Only by you typing the switch-back command yourself | On its own, once the task/topic it was invoked for is resolved |
| Can Claude revert it for you | No — no such action exists | Yes — that's the whole point of this rebuild |

An output style has no "revert automatically when the topic ends"
behavior available at all — that's a hard platform limit, not a wording
problem. A skill can behave that way because it was never a session-wide
switch in the first place.

## Files

- `.claude/skills/visual-learning-os/SKILL.md` — the skill itself:
  trigger rules, Mission, Core Principle, Response Structure, Teaching
  Mode, Work Recap & Feedback Mode, Existing System First, Knowledge
  Graph First, grounding rules, Golden Rules.
- `.claude/skills/visual-learning-os/reference/domain-modes.md` —
  architecture, framework/language learning, type-system rules, UI/
  design-system rules, API-layer rules, backend/database rules,
  native-wrapper rules, testing, component docs, founder mode, decision
  support, code explanation, debugging. Read on demand, not held in
  context for tasks that don't need it.
- `.claude/skills/visual-learning-os/reference/visual-style-guide.md` —
  visual design system, preferred visual formats, quality checklist,
  print-ready guide mode, render validation, documentation/guide
  generation. Also read on demand.
- `.claude/skills/visual-learning-os/stack-profile.template.md` — a
  blank template. **Copy it into each project as `stack-profile.md`
  and fill it in there** — never copy an already-filled one between
  projects (see below).

## How this behaves, exactly

1. **Manual only.** It never applies just because a topic looks
   related — you invoke it with `/visual-learning-os`, or by clearly
   asking for it by name.
2. **It can flag itself, never self-apply.** If a request looks like an
   unusually good fit, Claude may mention that once and ask — then
   waits for a yes. Silence or "no" means it proceeds normally.
3. **Scoped to the task/topic.** Once invoked, it stays active through
   natural follow-ups on that same thing, then hands back to normal
   default behavior once that task/topic is resolved — on its own, no
   extra command needed.
4. **Confirms both transitions.** It says when it starts ("Using Visual
   Learning OS for this.") and when it reverts ("(back to default
   style)") — never a silent switch either way.
5. **This is an instruction, not a hard platform switch.** Unlike the
   old output style, nothing external enforces the "manual only" or
   "reverts on its own" rules — Claude follows them because SKILL.md
   says to. It can misjudge where a topic ends, same as any instruction
   can be misjudged. If that ever happens noticeably, say so and it'll
   be tightened.

## Why project-scoped, not global

Every project gets its own copy of `stack-profile.md` describing its
actual stack. Work on two projects in a day and each keeps its own
profile — nothing gets mixed up or silently overwritten by whichever
project you touched most recently.

## One-time setup: create your personal template stash

Paste into Claude Code once, on any machine:

```
Set up the "visual-learning-os" skill as a project-scoped skill —
never at the user/global level, so different projects never share
or mix stack profiles.

1. Fetch these files from angelo5003/visual-learning-os, branch
   main, path .claude/skills/visual-learning-os/, into a personal
   template stash at ~/.claude/templates/visual-learning-os/:
   - SKILL.md
   - reference/domain-modes.md
   - reference/visual-style-guide.md
   - stack-profile.template.md
   This stash is a source to copy from only.

2. Confirm the files landed at the right paths and show me the
   directory listing.
```

## Per-project setup — repeat in each project (new or existing)

```
Install the visual-learning-os skill for this project from my
template stash at ~/.claude/templates/visual-learning-os/:

1. Copy SKILL.md and reference/ from the stash into
   ./.claude/skills/visual-learning-os/ in this project, unchanged.
2. Copy stack-profile.template.md from the stash to
   ./.claude/skills/visual-learning-os/stack-profile.md in this
   project, then fill it in by inspecting this project's
   package.json/requirements.txt/etc. and its own CLAUDE.md/AGENTS.md
   if either exists.
3. Show me the files you created and the filled-in profile.
```

That's it — no `.claude/settings.json` edit, no "activation" step.
Installing the files never changes how the project behaves by itself;
only invoking `/visual-learning-os` does, and only for that task.

## Using it

```
/visual-learning-os
```

Type that whenever you want it for the task at hand. It'll confirm it's
active, help with that task using everything above, then confirm when
it's reverted back to normal once the task/topic is done.

## Is this one-time, or do I run it every time?

- **Stash setup** → once per **laptop**. Do it again later only if you
  want to pull in an improved version of the skill.
- **Per-project file setup** (copying the files, creating the profile) →
  once per **project**.
- **Invoking it** (`/visual-learning-os`) → every time you want it for
  a specific task — that's the point, it's meant to be a deliberate,
  per-task choice, not something that stays on.

## Keeping projects up to date

When you improve `SKILL.md` or a reference file here, re-pull this repo
into your template stash, then re-copy `SKILL.md` and `reference/` into
each project's `.claude/skills/visual-learning-os/`. **Never** copy
`stack-profile.md` (the filled-in one) in either direction — only the
blank `stack-profile.template.md` is meant to travel between projects.

## Rules baked into the skill itself

- **Never installs a new MCP server, plugin, or skill on its own
  initiative.** It only uses tools already installed in your
  environment; if nothing installed matches what a task needs, it names
  what would help and asks before suggesting an install, falling back
  to official docs in the meantime.
- **Grounds Work Recap & Feedback Mode in real evidence** (the actual
  diff), never in memory of the conversation alone — feedback always
  cites a specific file/line, never generic praise.
- **Understanding comes before terminology** — no jargon before a plain-
  language explanation, whenever this skill is active.
