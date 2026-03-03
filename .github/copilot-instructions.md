# Copilot Instructions for ajaysingh.me

This is a Jekyll-based personal website and blog hosted on GitHub Pages, featuring a minimalist design with custom SASS styling and Rake automation.

## Architecture & Structure

**Layout Hierarchy**: default.html → page.html → [content.html | post.html | resume.html]
- `default.html`: Base wrapper with analytics (production only)
- `page.html`: Includes header/footer navigation
- `content.html`: Article wrapper for static pages
- `post.html`: Blog post layout with tags, prev/next navigation, and optional Disqus
- `resume.html`: Simplified article layout without header

**Content Organization**:
- Published posts go in `_posts/` (currently none; drafts in `_drafts/`)
- Static pages in `_pages/` with custom permalinks
- Home page ([index.html](index.html)) displays blog archives grouped by year

## CSS/SASS Conventions

**BEM-Style Naming**: Use strict prefixes for all custom classes
- `c-` prefix: Components (e.g., `c-article`, `c-page__header`, `c-archives__item`)
- `u-` prefix: Utilities (e.g., `u-container`, `u-separate`)

**SASS Structure** ([css/main.scss](css/main.scss)):
```
helpers/ → base/ → utilities/ → components/ → vendor/
```

**Color System** ([_sass/helpers/_variables.scss](_sass/helpers/_variables.scss)): Use predefined color variables
- Base colors: `$c-base__03` through `$c-base__3` (dark to light)
- Accents: `$c-accent__blue`, `$c-accent__darkblue`, `$c-accent__green`

## Development Workflow

**Local Development**:
```bash
bundle exec jekyll serve  # Standard Jekyll server
rake preview              # Preferred: Includes livereload (-L flag)
rake serve                # Alias for preview
```

**Creating Posts**: Use Rake for consistent formatting
```bash
rake post title="Post Title" [date="2026-03-02"] [tags=[tag1,tag2]] [category="Books"]
```
Creates file in `_posts/YYYY-MM-DD-slug.md` with standard front matter.

**Quality Checks**:
```bash
rake check   # Builds site and runs html-proofer for broken links
rake clean   # Remove _site directory
```

## Content Conventions

**Post Front Matter**:
```yaml
---
layout: post
title: "Post Title"
description: "Brief description (shows in archives)"
category: "Books"  # Optional, displayed if present
tags: [tag1, tag2]
---
```

**Page Front Matter**:
```yaml
---
layout: content  # or resume
title: "Page Title"
permalink: /about/  # Required for pages
---
```

## Key Configuration

- Analytics (Google Analytics) loads only when `jekyll.environment == 'production'`
- Disqus comments controlled by `site.disqus_id` (currently disabled)
- Site config in [_config.yml](_config.yml): title, author, social links, permalink format
- Navigation links hardcoded in [_includes/header.html](_includes/header.html)

## Project-Specific Notes

- No `_posts/` directory yet; content staged in `_drafts/`
- Rakefile includes colored console output helpers (Colors module)
- Uses `jekyll-livereload` and `jekyll-seo-tag` plugins
- Compiled CSS compressed in production via SASS config
- Baseurl extraction in Rakefile uses shell commands (awk/sed)
