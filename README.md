# Markdown Resume to PDF

[![Build and Release Resume PDF](https://github.com/denniskasper/resume/actions/workflows/release.yml/badge.svg)](https://github.com/denniskasper/resume/actions/workflows/release.yml)

Convert Markdown resumes to professionally styled PDFs using [md-to-pdf](https://github.com/simonhaenisch/md-to-pdf).

## Usage

Install dependencies:

```bash
npm install
```

Build PDF:

```bash
npm run build
```

Build HTML (for preview):

```bash
npm run build:html
```

## Deploying to denniskasper.com

The [denniskasper.com](https://github.com/denniskasper/denniskasper.com) site fetches the resume markdown and PDF at build time, and is hosted on [Cloudflare Workers](https://developers.cloudflare.com/workers/static-assets/) as static assets.

Deployment is fully automatic: on push to `main` here, the `release.yml` workflow builds the PDF, updates the `latest` GitHub release, then calls a Cloudflare Workers Deploy Hook to rebuild the site (which re-fetches this resume). No manual step is required.

The hook URL is stored in the `SITE_DEPLOY_HOOK_URL` repository secret, and the workflow fails if it is missing. If deploys stop working, check that the Deploy Hook still exists in the Worker's build settings in the Cloudflare dashboard and that the secret matches its URL.

## Customization

- Edit `dennis_kasper_resume.md` for content
- Edit `resume-style.css` for styling
