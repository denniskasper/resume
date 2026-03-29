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

The [denniskasper.com](https://github.com/denniskasper/denniskasper.com) site fetches the resume markdown and PDF at build time. After pushing changes and a new release is created, manually trigger a rebuild:

```bash
gh workflow run build-deploy.yaml --repo denniskasper/denniskasper.com
```

## Customization

- Edit `dennis_kasper_resume.md` for content
- Edit `resume-style.css` for styling

## Features

- Modern, professional styling
- Justified text for clean formatting
- Responsive section headers with accent colors
- Floating profile image
- Print-optimized CSS
