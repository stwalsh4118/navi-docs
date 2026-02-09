# navi-docs

Documentation site for [Navi](https://github.com/stwalsh4118/navi) — a TUI dashboard for monitoring and managing Claude Code sessions.

Built with [Starlight](https://starlight.astro.build), deployed to [Cloudflare Pages](https://pages.cloudflare.com).

## Local Development

```bash
pnpm install
pnpm dev
```

Opens at `http://localhost:4321`.

## Build & Deploy

```bash
pnpm build
```

Output goes to `./dist/`. Deploy to Cloudflare Pages automatically via GitHub integration, or manually:

```bash
npx wrangler pages deploy dist --project-name=navi-docs
```

## Updating Documentation

From the navi project directory, use the Claude Code skills:

- `/sync-docs` — Full project docs sync (discovers all Done PBIs, generates/updates pages, commits incrementally)
- `/document-feature <PBI-ID>` — Deep re-documentation of a single feature

The `.docs-manifest.json` tracks what's been documented with content hashes for incremental updates.

## Structure

```
src/content/docs/
  index.mdx                     # Landing page
  getting-started/              # Installation & configuration
  features/                     # Feature documentation (one page per feature)
  architecture/                 # System architecture, data flow, hooks, providers
  reference/                    # Keybindings, config files, JSON formats, status icons
  changelog.md                  # Feature completion history
```
