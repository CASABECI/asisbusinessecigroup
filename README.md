# ASIS Business Ecigroup

A production-ready SvelteKit website for **asisbusinessecigroup.com**, designed for Cloudflare deployment and focused on clear messaging, responsive design, and business credibility.

## Overview

This project replaces the previous repository contents with a fresh SvelteKit application that includes:

- A responsive marketing website for ASIS Business Ecigroup
- Dedicated Home, Services, About, Contact, and error pages
- Reusable Navbar and Footer components
- Mobile-first layouts using CSS Grid and Flexbox
- SEO metadata on every page
- Cloudflare deployment configuration and GitHub Actions workflow

## Tech Stack

- **Framework:** SvelteKit
- **Language:** TypeScript
- **Build Tool:** Vite
- **Adapter:** `@sveltejs/adapter-cloudflare`
- **Deployment Target:** Cloudflare Pages / Cloudflare-compatible output

## Project Structure

```text
.
├── .github/workflows/deploy.yml
├── src/
│   ├── app.html
│   ├── lib/components/
│   │   ├── Footer.svelte
│   │   └── Navbar.svelte
│   └── routes/
│       ├── +error.svelte
│       ├── +layout.svelte
│       ├── +layout.ts
│       ├── +page.svelte
│       ├── about/+page.svelte
│       ├── contact/+page.svelte
│       └── services/+page.svelte
├── static/
│   ├── favicon.ico
│   └── robots.txt
├── .env.example
├── .gitignore
├── package.json
├── svelte.config.js
├── tsconfig.json
├── vite.config.ts
├── wrangler.toml
└── README.md
```

## Pages Included

### Home
- Hero section with brand positioning
- Value propositions
- Services preview cards
- CTA section
- Newsletter signup with validation

### Services
- Six professional service cards
- Hover interactions
- CTA for custom engagements

### About
- Company story
- Mission and vision
- Leadership team section
- Core values
- Why choose us summary

### Contact
- Client-side validated contact form
- Email, phone, and office details
- Social links

### Error Page
- Professional 404 / error state experience
- Recovery links back to the site

## Design System

Global styles are defined in `src/routes/+layout.svelte` and include:

- Primary: `#1e3a5f`
- Secondary: `#2d6a9f`
- Accent: `#f0a500`
- Light: `#f8f9fa`
- Dark text: `#212529`
- Breakpoints at `768px` and `1024px`
- Google Font import for modern typography

## Environment Variables

Copy `.env.example` to `.env` and update values as needed:

```bash
cp .env.example .env
```

Available variables:

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`
- `PUBLIC_GA_MEASUREMENT_ID` (optional)

## Local Development

Install dependencies and start the development server:

```bash
npm install
npm run dev
```

Useful scripts:

```bash
npm run dev
npm run build
npm run preview
npm run check
```

## Deployment

### GitHub Actions

The workflow in `.github/workflows/deploy.yml` runs on pushes and pull requests targeting the `stable` branch. It:

1. Checks out the repository
2. Sets up Node.js 20
3. Installs dependencies with `npm ci`
4. Builds the SvelteKit site
5. Deploys to Cloudflare Pages using repository secrets

### Required GitHub Secrets

Add these secrets to the repository before enabling deployment:

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`
- `GITHUB_TOKEN` is provided automatically by GitHub Actions

## SEO Notes

Each page includes:

- Page-specific `<title>` tags
- Meta descriptions
- Canonical links
- Open Graph basics on the home page
- `robots.txt` pointing to the production sitemap URL

## Notes

- `src/app.html` is included because SvelteKit requires it at runtime.
- `static/favicon.ico` is a simple placeholder icon that can be replaced with a branded asset later.
- The contact and newsletter forms currently provide client-side feedback and are ready to be connected to a backend or form service.

## Next Recommended Steps

1. Add a branded favicon and social share image
2. Connect the contact form to an email or CRM workflow
3. Add analytics using `PUBLIC_GA_MEASUREMENT_ID`
4. Create a sitemap endpoint or static sitemap file for production
