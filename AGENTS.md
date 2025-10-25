# Repository Guidelines

## Project Structure & Module Organization
The Astro app lives at `src/`, split into `pages/` for routes, `layouts/` for reusable templates, and `content/` for the content collection schema plus Markdown posts under `content/blog/`. Static assets belong in `public/`. Build output is written to `dist/` after a production build. Configuration surfaces in `astro.config.mjs`, `tsconfig.json`, and deployment presets in `vercel.json` and `netlify.toml`.

## Build, Test, and Development Commands
- `npm install` fetches dependencies; run once per environment.
- `npm run dev` starts the Astro dev server at `http://localhost:4321` with hot reload.
- `npm run build` bundles the static site into `dist/` for deployment.
- `npm run preview` serves the most recent build locally for smoke checks.
- `npm run astro check` (or `npx astro check`) performs content and TypeScript diagnostics; use it before opening a PR.

## Coding Style & Naming Conventions
Favor two-space indentation across `.astro`, `.ts`, and Markdown files. Keep Astro components small and colocate component styles in the same file. Use PascalCase for components, camelCase for TypeScript variables, and kebab-case filenames for Markdown posts (e.g., `writing-fast-notes.md`). Frontmatter must include `title`, `description`, and `date`; set `draft: true` to keep posts out of production. Run `astro check` and rely on Astro’s formatter (`npx astro format`) when touching templates.

## Testing Guidelines
Formal automated tests are not yet present; rely on `npm run astro check` for schema and type safety, then use `npm run preview` to verify navigation and rendering. Add integration tests alongside future features—place Playwright suites under `tests/` and snapshot assets in `tests/__snapshots__/` to keep the structure predictable. Document new test commands in `package.json`.

## Commit & Pull Request Guidelines
Commit messages in the history use concise, imperative summaries (e.g., “Add hyper minimal monospace theme”). Follow that pattern and group related changes. Open PRs with a short summary, bullet highlights, linked issue or ticket, and screenshots or GIFs when UI shifts. Include verification notes (dev server, preview, or production deploy) so reviewers can trust the change. Keep PRs scoped: new posts, design tweaks, and configuration updates each merit independent reviews.

## Content Contribution Tips
Draft new posts in `src/content/blog/` and preview via `npm run dev` to confirm metadata in the listing. Upload images to `public/` and reference them with root-relative paths (e.g., `/images/diagram.png`). When retiring posts, leave the file in place and set `draft: true` to keep permalinks intact.
