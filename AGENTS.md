# Repository Guidelines

## Project Structure & Module Organization

This repository is a Jekyll personal site and blog. Site configuration lives in
`_config.yml`; the entry page is `index.html`. Static content belongs in
`_pages/`, unpublished writing in `_drafts/`, and published posts in
`_posts/` (create that directory before using the post generator if it is
absent). Templates are in `_layouts/`, reusable fragments in `_includes/`, and
SASS sources in `_sass/`, imported by `css/main.scss`. Images and other public
assets live in directories such as `resume/`. Generated `_site/` output should
not be edited or committed.

## Build, Test, and Development Commands

Run `bundle install` after cloning or changing dependencies.

- `bundle exec jekyll serve` starts the standard local server.
- `rake preview` (or `rake serve`) cleans generated output and starts Jekyll
  with livereload; plain `rake` invokes the same preview task.
- `bundle exec jekyll build` produces the site in `_site/`.
- `rake check` builds the site and runs `htmlproofer` against `_site/` for link
  and markup issues.
- `rake clean` removes generated `_site/` output.
- `rake post title="A Title" date="YYYY-MM-DD" tags="[tag]"` scaffolds a post
  with the repository’s front matter (after `_posts/` exists).

## Coding Style & Naming Conventions

Use two-space indentation in Markdown, YAML, HTML, Ruby, and SASS. Keep page
front matter explicit (`layout`, `title`, and `permalink`). Follow the SASS
load order in `css/main.scss` and use the existing variables in
`_sass/helpers/_variables.scss`. Custom CSS classes use BEM-style names with
`c-` for components and `u-` for utilities (for example, `c-article` and
`u-container`). Keep generated or cache files out of changes.

## Testing Guidelines

There is no unit-test suite or coverage requirement. Treat `rake check` as the
required site validation, and manually inspect changed pages with the local
server, especially after layout or SASS changes.

## Commit & Pull Request Guidelines

Use short, imperative, focused commit subjects, consistent with existing
history (for example, `Update about.md` or `chore(updates): bump`). Keep
dependency-only updates separate from content or design changes. Pull requests
should explain the change, identify affected pages or configuration, include
validation results (`rake check`), and attach screenshots for visual changes.
