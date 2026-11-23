# Astro Blog Starter Template

A blog starter built with Astro, Markdown/MDX, RSS, sitemap generation, and the Cloudflare adapter. Static assets are served through Cloudflare Workers.

## Requirements

- Node.js 22 or later, matching `package.json` and `.nvmrc`.
- npm, with the committed `package-lock.json` used for reproducible installs.

If you use `nvm`, select the documented version with `nvm use`.

## Local development

```bash
npm ci
npm run dev
```

Astro prints the local development URL, normally `http://localhost:4321`.

Content collections live in `src/content/`, routes live in `src/pages/`, reusable components live in `src/components/`, and static files live in `public/`.

## Validation

```bash
npm run check
```

This command runs:

1. `astro build` to create the production site.
2. `tsc` to check TypeScript.
3. `wrangler deploy --dry-run` to validate the Worker bundle without deploying it.

The check does not intentionally deploy the site. It does not replace browser, accessibility, or visual review of the rendered pages.

## Before production

- Replace the placeholder `site: "https://example.com"` in `astro.config.mjs` with the real public site URL so canonical URLs, RSS, and sitemap entries are correct.
- Review the Worker configuration and provide any required Cloudflare credentials through the appropriate local or CI secret mechanism.
- Review the generated site and deployment settings before publishing.

## Commands

| Command | Purpose |
| --- | --- |
| `npm run dev` | Start the Astro development server. |
| `npm run build` | Build the production site. |
| `npm run preview` | Build and run locally through Wrangler. |
| `npm run check` | Build, type-check, and perform a deployment dry run. |
| `npm run cf-typegen` | Regenerate Cloudflare binding types. |
| `npm run deploy` | Deploy to Cloudflare; run only after explicit review and authorization. |
| `npx wrangler tail` | View logs for the configured deployed Worker. |

## Credit

This theme is based on [Bear Blog](https://github.com/HermanMartinus/bearblog/).
