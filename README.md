# Visual Learning OS v5 — template

This branch holds only the stack-agnostic parts of the Visual Learning OS
v5 output style: the core file and its two reference files. There is no
`stack-profile.md` and no `.claude/settings.json` here on purpose — this
branch is a source to copy from, not something to activate directly.

## Files

- `.claude/output-styles/visual-learning-os-v5.md` — the core output
  style.
- `.claude/output-styles/reference/domain-modes.md` — architecture,
  framework/language learning, type-system rules, UI/design-system
  rules, API-layer rules, backend/database rules, native-wrapper rules,
  testing, component docs, founder mode, decision support, code
  explanation, debugging.
- `.claude/output-styles/reference/visual-style-guide.md` — visual
  design system, preferred visual formats, quality checklist,
  print-ready guide mode, render validation, documentation/guide
  generation.

## How to use this in a project (new or existing)

1. Copy `visual-learning-os-v5.md` and `reference/` into that project's
   own `.claude/output-styles/`.
2. In that project's own `.claude/settings.json`, set:
   ```json
   { "outputStyle": "Visual Learning OS v5" }
   ```
3. Create `.claude/output-styles/stack-profile.md` **in that project**
   describing its actual stack — never copy one in from here or from
   another project. See the "Project Stack Profile" section in the core
   file for what it should cover and how it gets filled in.

## Keeping projects up to date

When you improve the core file or a reference file, re-pull this branch
and re-copy those two things into each project's `.claude/output-styles/`.
Never copy `stack-profile.md` in either direction — it's the one file
that stays project-specific.
