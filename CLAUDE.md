# Claude context for the Dataleap docs

Read AGENTS.md first — it has the core project instructions and terminology rules.
This file adds the working context from the docs rebuild (July 2026).

## Current state

- The full docs restructure lives on branch `docs-restructure` (PR against main). PR #1 (video series) and PR #2 (light-mode hotfix) are merged and live.
- Preview: `mint dev` on localhost:3000, hot-reloads on save. Verify with `mint validate` and `mint broken-links` before finishing.
- Simon has reviewed ALL chapters page by page (Jul 2026), including admin (rewritten from real admin-panel screenshots) and FAQ.
- Ch4 decisions: templates split into `share/templates.mdx` (open) + `share/locked-templates.mdx`; NO "sharing by copying" anti-pattern anywhere; no trigger-copy warning on team-spaces (canonical stays on triggers page); team-spaces kept short and purpose-first.
- Chapter overview pages list ONLY their own chapter's pages (no cross-chapter cards); cards are title + one sentence, no bullets.
- Admin chapter reflects the real admin panel (app.dataleap.ai/admin): Organization (org-wide system prompt), Members/Teams, Budgets (hard weekly caps, user→team→org-default resolution), Analytics (per-agent list with AI summaries), Apps & Permissions (tool-level allow/deny), Tool Requests, App Activity, MCP servers.
- Chat upload limit is 5 MB (FAQ); Knowledge panel limit 10 MB (add-knowledge).

## Structure & storyline

Chapters are numbered and mirror the video series, plus Admin:
Ch1 `introduction/` → Ch2 `build/` → Ch3 `scale/` → Ch4 `share/` → Ch5 `admin/`, then `video-series/` and `faq.mdx` (FAQ is deliberately LAST, own nav group).
Chapter overview pages are titled "Chapter N: <Name>" with NO sidebarTitle — Mintlify's prev/next pagination uses that title, so chapter transitions are explicit. Old flat URLs redirect via `docs.json`.

## Voice & product truths (from Simon's reviews — do not regress)

- **Chat-first everywhere.** Users build, refine, connect, and give feedback in the agent's chat. Never write click-path instructions for things the chat does (the exception: genuinely UI-based flows like the Skills section, Settings > Connected Apps overview, Versions tab).
- **Sub-agents and PTC are theoretical concepts.** Dataleap applies them automatically; users can't create/skip them. The ONE user action: ask the agent "Would PTC make sense here?" / adjust intelligence levels.
- **Model tiers:** Expert (build) / Pro (run default, ~90%) / Standard (dial down when proven). Adjust by evidence, two paths: runs fine → lower; misses info/times out → raise.
- **Connections have two levels:** account-level connect (once, OAuth) + per-workflow permission activation (visible labels, as-small-as-possible set, Approve All). Dataleap handles minimal access — don't preach pruning to builders (admin page covers governance).
- **Triggers:** event-based OFTEN best (not "almost always"); universal rule = be as precise as possible. Copied agents carry triggers but they start DISABLED. No "one run per item" concept.
- **Skills:** ONE definition (the "reusable part of an agent" one, in the frontmatter description only). Create = from agent chat OR Skills section (Create in Chat / Create Manually / Import Markdown) — shown as Tabs. Use = reference the skill explicitly in the agent. Share = Personal / Team / Org. Skills-vs-knowledge only as a short bottom note.
- **Versioning replaced duplication:** restore via chat "Restore to this version" or Workflow → Versions tab. No duplicate-to-experiment advice.
- **One agent, one responsibility; one chat window = one agent.** No "add one capability at a time", no "5–10 examples" testing rule — build, test once, let it run, refine from real results.
- Steps component only for real sequences (parallel options → Tabs or tables; non-sequential lists → tables).
- Exact numbers to preserve: $50 vs $0.50/month (~100x) trigger example; PTC 30–80% + 570s/200credits vs 60s/40credits; tiers ~3–4x.

## Images

- Product screenshots live in `images/` (PNG). Simon supplies them via Desktop (Cmd+Shift+4 files — chat-pasted images can NOT be extracted). Annotate highlights (indigo rounded rects via PIL) like versioning-restore-chat.png; crop out irrelevant UI/PII where possible.
- Diagrams are hand-built SVG pairs (`*-light.svg`/`*-dark.svg`) embedded via Frame + `className="block dark:hidden"` pattern. Do NOT inline SVG in MDX (sanitizer strips text/circle). No caption text inside SVGs — use the Frame caption. Connectors: tree/elbow style ending at card edges, never crossing content.
- Genericize customer names in examples (no Sennder/EGYM specifics in rendered content).
- Appearance is forced light (`docs.json` appearance strict); dark-safe CSS + dark SVG variants kept in case dark returns.

## Open items

- One screenshot TODO: the template library (sidebar > Templates or a team space's Templates tab) for the deploy section on share/templates.
- Confirm the Knowledge panel upload limit (docs say 10 MB; chat is confirmed 5 MB).
