> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is Dataleap's end-user documentation site built on [Mintlify](https://mintlify.com)
- The primary audience is regular app users who want to discover features and use the product successfully
- The app source of truth is in `/Users/rizqitsani/Documents/Work/Dataleap/tahoe`
- Document the shipped product at `https://app.dataleap.ai`, not roadmap ideas or internal-only behavior
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links
- Run `mint validate` before finishing substantial docs changes

## Terminology

- Use "agent" for the thing a user creates and runs
- Use "Connected Apps" for the product area and UI label; use "connected app" in normal prose
- Use "template" for a reusable starting point from the **Templates** area
- Use "run" for a single execution of an agent
- Use "knowledge" for uploaded reference files attached to an agent
- Use "instructions" for how an agent should behave
- Use "workflow" only when the UI uses that label or when describing a template's workflow
- Use "team" for shared group features; do not replace it with "workspace" unless the UI says "workspace"
- Use "usage" and "credits" the way the product UI does
- Do not use the internal product codename "Tahoe" in end-user docs

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- Start with the user's goal, then explain how to do it
- Prefer task-based page titles and headings such as "Connect apps" or "Inspect a run"
- Match UI capitalization exactly for product labels such as **New Agent**, **Agents**, **Templates**, **Usage**, **Connected Apps**, **Knowledge**, **Workflow**, **Runs**, and **Settings**
- Prefer concrete product actions over abstract feature descriptions
- Avoid marketing language, hype, and claims that are not visible in the product
- Add prerequisites near the top when a task depends on setup or permissions
- Keep examples realistic and product-specific

## Content boundaries

- Document shipped end-user features only
- Do not describe planned or future features as if they are available
- Do not document internal admin routes, sandbox pages, experiments, analytics tooling, feature flags, or implementation details unless the user explicitly asks for internal docs
- Do not document developer architecture, backend internals, or vendor plumbing such as WorkOS, Nango, PostHog, or WebSocket behavior in end-user docs unless a user must interact with it directly
- Do not document features that appear unfinished or are marked "coming soon" as available product functionality
- Focus on regular users first; only document team admin flows when they are explicitly requested or necessary to complete a user-facing workflow
- Prefer the live app UI and app source over marketing copy when they differ
