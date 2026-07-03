# Project Guidelines

## Overview
Personal academic/portfolio website for Umut Soysal, built with **Jekyll** (Academic Pages theme, "air" variant) and hosted on **GitHub Pages** at `https://umutsoysal.github.io`.

## Architecture
- `_config.yml` — site-wide settings (title, author, theme, URLs)
- `_data/navigation.yml` — header nav tabs; add new tabs here
- `_pages/` — standalone pages (Markdown or HTML with YAML front matter)
- `_publications/`, `_posts/`, `_talks/`, `_teaching/` — content collections
- `_includes/`, `_layouts/`, `_sass/` — theme templates and styles
- `assets/`, `images/`, `files/` — static assets

## Adding Content
- **New page**: create `_pages/<slug>.md` with `layout`, `title`, `permalink` front matter, then add a nav entry to `_data/navigation.yml`
- **New publication**: create `_publications/<date>-<slug>.md` following the existing file format
- **Style overrides**: add to `assets/css/main.scss` after the `@import` block — do not edit `_sass/vendor/`

## Deployment
- Deployment is automatic via the built-in `pages-build-deployment` GitHub Actions workflow on every push to `master`
- No manual build step needed; just `git push origin master`
- Local build requires Ruby ≥ 3.0 (`bundle exec jekyll serve`)

## Conventions
- Front matter delimiters are `---`
- Use `permalink: /<slug>/` (with trailing slash) for all pages
- Keep nav titles short (≤ 12 chars) to avoid header overflow
- Do not commit `_site/` changes directly — it is regenerated on deploy
