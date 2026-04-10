# Beam Analytics — Next.js Example

Add privacy-first, cookie-free analytics to your Next.js app in 2 minutes.

## Prerequisites

- Node.js 18+
- A Beam account (free at [beam-privacy.com](https://beam-privacy.com))
- Your Beam `SITE_ID` from the dashboard

## Setup

### 1. Clone this example

```bash
git clone https://github.com/scobb/beam-examples.git
cd beam-examples/examples/nextjs
npm install
```

### 2. Configure your site ID

```bash
cp .env.example .env.local
# Edit .env.local and set NEXT_PUBLIC_BEAM_SITE_ID=your_site_id_here
```

### 3. Run the app

```bash
npm run dev
# Visit http://localhost:3000 — Beam will track pageviews
```

### 4. Verify

Open your [Beam dashboard](https://beam-privacy.com/dashboard) and check for the pageview.

---

## Integration Guide

### App Router (Next.js 13+)

In `app/layout.tsx`:

```tsx
import Script from 'next/script'

export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="en">
      <head>
        <Script
          defer
          src="https://beam-privacy.com/js/beam.js"
          data-site-id={process.env.NEXT_PUBLIC_BEAM_SITE_ID}
          strategy="afterInteractive"
        />
      </head>
      <body>{children}</body>
    </html>
  )
}
```

### Pages Router (Next.js 12 and older)

In `pages/_app.tsx`:

```tsx
import Script from 'next/script'
import type { AppProps } from 'next/app'

export default function App({ Component, pageProps }: AppProps) {
  return (
    <>
      <Script
        defer
        src="https://beam-privacy.com/js/beam.js"
        data-site-id={process.env.NEXT_PUBLIC_BEAM_SITE_ID}
        strategy="afterInteractive"
      />
      <Component {...pageProps} />
    </>
  )
}
```

### Custom Event Tracking

```tsx
// Track a button click
<button onClick={() => window.beam?.track('cta_click', { location: 'hero' })}>
  Get Started
</button>
```

### TypeScript Support

```bash
npm install --save-dev @keylightdigital/beam
```

This adds `window.beam.track()` type declarations.

---

## More Resources

- Full Next.js guide: https://beam-privacy.com/for/nextjs
- Live demo: https://beam-privacy.com/demo
- Signup: https://beam-privacy.com/signup
