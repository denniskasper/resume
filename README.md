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

The [denniskasper.com](https://github.com/denniskasper/denniskasper.com) site fetches the resume markdown and PDF at build time, and is hosted on a [Dokploy](https://dokploy.com/) server that auto-deploys on every push to its `main` branch.

Deployment is fully automatic: on push to `main` here, the `release.yml` workflow builds the PDF, updates the `latest` GitHub release, then pushes an empty commit to the denniskasper.com repo to trigger a Dokploy redeploy (which re-fetches this resume). No manual step is required.

This cross-repo push uses the `SITE_DEPLOY_TOKEN` repository secret — a fine-grained PAT scoped to the denniskasper.com repo with **Contents: read/write**. If deploys stop working, check whether that token has expired and regenerate it.

## Customization

- Edit `dennis_kasper_resume.md` for content
- Edit `resume-style.css` for styling
