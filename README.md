# beam-examples

Working integration examples for [Beam](https://beam-privacy.com) — privacy-first, cookie-free web analytics.

[![Beam](https://img.shields.io/badge/Powered%20by-Beam-4f46e5)](https://beam-privacy.com)
[![npm](https://img.shields.io/npm/v/@keylightdigital/beam)](https://www.npmjs.com/package/@keylightdigital/beam)

## Examples

| Framework | Example | Description |
|-----------|---------|-------------|
| [Next.js](./examples/nextjs/) | `examples/nextjs/` | App Router + Pages Router integration with `next/script` |
| [Astro](./examples/astro/) | `examples/astro/` | Astro layout integration via `<head>` |
| [SvelteKit](./examples/sveltekit/) | `examples/sveltekit/` | SvelteKit integration in `app.html` |

Each example includes:
- ✅ `README.md` with "Run in 2 minutes" instructions
- ✅ `.env.example` for your Beam `SITE_ID`
- ✅ Minimal project structure ready to run

## Quick Start

1. Sign up at [beam-privacy.com](https://beam-privacy.com) (free tier available)
2. Add a site in the dashboard and copy your `site_id`
3. Pick the example that matches your framework
4. Follow the README in that folder

## Installation

```bash
npm install @keylightdigital/beam
```

Or use the script tag directly:

```html
<script defer src="https://beam-privacy.com/js/beam.js" data-site-id="YOUR_SITE_ID"></script>
```

## What Beam Tracks

- Page URL and path
- Referrer source
- Screen width (device type detection)
- Country (from Cloudflare headers — no IP stored)
- Browser
- Language

**What Beam does NOT track:** cookies, IP addresses, personal data, fingerprinting, localStorage

## Links

- 🌐 Product: https://beam-privacy.com
- 🚀 Live demo: https://beam-privacy.com/demo
- 📚 Docs: https://beam-privacy.com/docs/api
- 📦 npm: https://www.npmjs.com/package/@keylightdigital/beam
- 🔒 Privacy: https://beam-privacy.com/privacy
- ⭐ Main repo: https://github.com/scobb/beam

## License

MIT — see individual example directories.