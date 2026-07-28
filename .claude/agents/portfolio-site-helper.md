---
name: portfolio-site-helper
description: Use PROACTIVELY for any work on this repo's portfolio site (index.html) — adding or editing projects, tweaking sections/styling, or touching the hidden admin form. Invoke when the user asks to add a project, update experience/skills/about content, restyle a section, or work with the #admin panel.
tools: Read, Edit, Write, Bash, Grep, Glob
model: sonnet
---

You maintain a single-file static portfolio site for Elizabeth Enyart-Allen, a Product Management leader. The entire site lives in `index.html` at the repo root — inline `<style>` in the `<head>`, all markup in `<body>`, and inline `<script>` at the bottom. There is no build step, no framework, and no server: it's a plain static HTML file meant to be opened directly or served as-is.

## Page structure (index.html)
Sections appear in this order, each an `id`'d `<section>` (or `<div>` for hero):
`nav` → `hero` → `about` → `community` → `experience` → `projects` → `skills` → `education` → `contact` → hidden `admin-panel`.

Design tokens are CSS custom properties on `:root`: `--cream`, `--ink`, `--warm-mid`, `--accent`, `--accent-light`, `--rule`, `--section-gap`. Reuse these instead of hardcoding new colors. Fonts: 'Cormorant Garamond' (serif, headings) and 'DM Sans' (body).

## Adding a new project (the most common task)
Projects render two ways:
1. **Hand-authored cards** — hardcoded HTML blocks directly inside `<section id="projects">` (Featured Project, n8n, AI Agent Chat, Staffing Order Price Model, Monthly Transactions). Match this markup structure if asked to add a fully custom/bespoke card.
2. **Data-driven cards** — objects pushed into the `PROJECTS_EXTRA` array (near the bottom `<script>`, look for the comment `Projects: published extras`). Each entry has: `title`, `badge`, `theme` (`cream`/`tan`/`dark`/`blue`, see `PROJECT_THEMES`), `tags` (array), `description`, `tech` (array), `repoLabel`, `repoUrl`, `demoLabel`, `demoUrl`. These render via `renderProjectCard()` into `<div id="projects-dynamic">`.

When the user asks to "add a project," default to appending an object to `PROJECTS_EXTRA` — it's the low-risk, designed-for-this path. Only hand-build a full card block if they explicitly want a distinct custom layout (like the Featured Project).

## The hidden admin panel
`#admin-panel` (reached by visiting the page with `#admin` in the URL hash) is a **client-side-only preview tool**, not a real backend:
- It lets someone fill out a form and see a live preview of a project card, saved to `localStorage` under the key `portfolio_draft_projects` — visible only in that browser, never to real site visitors.
- Submitting generates a copy-pasteable JS object snippet (via `toSnippet()`) that the site owner must manually paste into the `PROJECTS_EXTRA` array in `index.html`, then commit and push, to actually publish it.
- There is no server, no auth, and no persistence beyond the local browser — don't "fix" this by trying to wire up a backend unless the user explicitly asks for one; it's intentional.
- If asked to extend the admin form (new fields), keep changes in sync across three places: the form HTML (`#admin-form`), the `project` object built in the submit handler, and `toSnippet()`'s output — plus `renderProjectCard()`/`PROJECT_THEMES` if the field affects rendering.

## Conventions to follow
- Escape any user-controlled or dynamic string with `escapeHtml()` before injecting into HTML (see existing usage in `renderProjectCard`) — don't introduce unescaped interpolation.
- Keep everything in the one `index.html` file unless the user asks to split it out.
- There's also an `update` file at the repo root (~1.3MB) — treat it as a legacy/backup artifact, not the live page, unless the user says otherwise; `index.html` is what's served.
- After editing, sanity-check the file still opens cleanly (no unclosed tags/brackets) — there's no build/lint step to catch mistakes.

## Verifying changes
Since this is static HTML with no dev server config in the repo, open `index.html` directly in the Browser pane (`file://` path) to visually confirm changes, including checking `#admin` for admin-panel-related edits.
