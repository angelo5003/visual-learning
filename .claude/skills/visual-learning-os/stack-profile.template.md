# Project Stack Profile — template (copy this, don't reference it directly)

> **Do not sync this file.** `SKILL.md` and `reference/` are meant to be
> identical copies pulled from your personal template stash — safe to
> overwrite whenever you improve the skill. This file is the opposite: it
> describes *this specific repo* and must never be replaced by a copy
> from another project or from the template stash.

Fill this in the first time this skill is used in this repo, by reading
`package.json`/`requirements.txt`/`go.mod`/etc. and any existing
`CLAUDE.md`/`AGENTS.md`. Update it if the stack changes.

- **Language(s) & version constraints:** _e.g. TypeScript (strict)_
- **Framework(s):** _e.g. React 19 + Next.js 16 (App Router)_
- **Runtime/deployment shape:** _e.g. static export, server-rendered,
  serverless — this determines which framework features actually apply_
- **UI/design system, if any:** _e.g. a component library + custom design
  tokens, with their file locations_
- **Data layer:** _e.g. REST/GraphQL/tRPC + ORM/BaaS, or "none yet —
  pre-backend"_
- **Native/cross-platform wrapper, if any:** _e.g. Capacitor/Electron/React
  Native, or "web only"_
- **Test tooling:** _e.g. unit/component runner, e2e runner, component
  documentation tool_
- **Code-structure/knowledge tools available:** _any MCP server or CLI
  that exposes call graphs, symbol search, or impact analysis for this
  repo — name it here if one exists; otherwise Grep/Glob/Read are the
  only exploration tools and the Knowledge Graph First section in
  SKILL.md does not apply_
- **Docs-grounding source:** _this project's own grounding hierarchy for
  "which docs to check before writing framework code" — usually in
  `CLAUDE.md`/`AGENTS.md` if either exists_

When this file is empty or stale, say so and ask before assuming
stack-specific behavior — don't silently reuse a previous project's stack.
