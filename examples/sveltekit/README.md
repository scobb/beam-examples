# Beam Analytics — SvelteKit Example

Add privacy-first, cookie-free analytics to your SvelteKit app in 2 minutes.

## Prerequisites

- Node.js 18+
- A Beam account (free at [beam-privacy.com](https://beam-privacy.com))
- Your Beam `SITE_ID` from the dashboard

## Setup

### 1. Clone this example

```bash
git clone https://github.com/scobb/beam-examples.git
cd beam-examples/examples/sveltekit
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
# Visit http://localhost:5173 — Beam will track pageviews
```

### 4. Verify

Open your [Beam dashboard](https://beam-privacy.com/dashboard) and check for the pageview.

---

## Integration Guide

### In `app.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    %sveltekit.head%
    <script defer src="https://beam-privacy.com/js/beam.js" data-site-id="%PUBLIC_BEAM_SITE_ID%"></script>
  </head>
  <body data-sveltekit-preload-data="hover">
    <div style="display: contents">%sveltekit.body%</div>
  </body>
</html>
```

### Alternative: In a `+layout.svelte`

```svelte
<script>
  import { onMount } from 'svelte';
  import { PUBLIC_BEAM_SITE_ID } from '$env/static/public';
</script>

<svelte:head>
  <script defer src="https://beam-privacy.com/js/beam.js" data-site-id={PUBLIC_BEAM_SITE_ID}></script>
</svelte:head>

<slot />
```

### Custom Event Tracking

```svelte
<script>
  function handleClick() {
    window.beam?.track('cta_click', { location: 'hero' });
  }
</script>

<button on:click={handleClick}>Get Started</button>
```

### TypeScript Support

```bash
npm install --save-dev @keylightdigital/beam
```

Adds `window.beam.track()` type declarations for full IDE support.

---

## More Resources

- Live demo: https://beam-privacy.com/demo
- Signup: https://beam-privacy.com/signup
- All framework guides: https://beam-privacy.com/for
