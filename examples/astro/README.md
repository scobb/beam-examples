# Beam Analytics — Astro Example

Add privacy-first, cookie-free analytics to your Astro site in 2 minutes.

## Prerequisites

- Node.js 18+
- A Beam account (free at [beam-privacy.com](https://beam-privacy.com))
- Your Beam `SITE_ID` from the dashboard

## Setup

### 1. Clone this example

```bash
git clone https://github.com/scobb/beam-examples.git
cd beam-examples/examples/astro
npm install
```

### 2. Configure your site ID

```bash
cp .env.example .env
# Edit .env and set PUBLIC_BEAM_SITE_ID=your_site_id_here
```

### 3. Run the app

```bash
npm run dev
# Visit http://localhost:4321 — Beam will track pageviews
```

### 4. Verify

Open your [Beam dashboard](https://beam-privacy.com/dashboard) and check for the pageview.

---

## Integration Guide

### In a Layout component (`src/layouts/Layout.astro`)

```astro
---
// src/layouts/Layout.astro
const siteId = import.meta.env.PUBLIC_BEAM_SITE_ID;
---

<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>My Site</title>
    <script defer src="https://beam-privacy.com/js/beam.js" data-site-id={siteId}></script>
  </head>
  <body>
    <slot />
  </body>
</html>
```

### Custom Event Tracking

```html
<button onclick="window.beam?.track('cta_click', { page: 'home' })">
  Get Started
</button>
```

Or in a `.astro` component:

```astro
<script>
  document.querySelector('#cta')?.addEventListener('click', () => {
    window.beam?.track('cta_click', { page: 'home' })
  })
</script>
```

### TypeScript Support

```bash
npm install --save-dev @keylightdigital/beam
```

Adds `window.beam.track()` type declarations for full IDE support.

---

## More Resources

- Full Astro guide: https://beam-privacy.com/for/astro
- Live demo: https://beam-privacy.com/demo
- Signup: https://beam-privacy.com/signup
