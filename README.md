# Gjope GitHub Pages Blog

This repository contains the source for the **Gjope** GitHub Pages website. The site is publicly available at **https://gjope.github.io/**. It is a [Jekyll](https://jekyllrb.com/) powered blog that uses the default `minima` theme and the GitHub Pages toolchain defined in the `Gemfile`.

## Table of Contents
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installing Dependencies](#installing-dependencies)
- [Running the Site](#running-the-site)
  - [Development](#development)
  - [Production Build](#production-build)
- [Project Structure](#project-structure)
- [Content Workflow](#content-workflow)
- [Testing and Validation](#testing-and-validation)
- [Contributing](#contributing)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [TODO](#todo)

## Getting Started

### Prerequisites
- Ruby (MRI) and Bundler installed locally. `github-pages` (the dependency that powers the site) documents the supported Ruby versions. **TODO:** Confirm the exact Ruby version currently used in production.
- A working installation of `make`, `gcc`, and other build tools if you are on Linux or macOS (these are required to build native gems).
- Access to clone this repository.

### Installing Dependencies
1. Install Bundler if you do not already have it:
   ```bash
   gem install bundler
   ```
2. Install the Ruby gem dependencies listed in the `Gemfile`:
   ```bash
   bundle install
   ```

## Running the Site

### Development
Run the Jekyll development server with automatic regeneration:
```bash
bundle exec jekyll serve
```
This starts a local web server (default `http://127.0.0.1:4000/`) that watches for changes and rebuilds the site automatically. When you edit files under `_posts/`, `_layouts/`, `_includes/`, or other content directories, refresh the browser to see your updates.

### Production Build
Generate the static site locally in the `_site/` folder:
```bash
bundle exec jekyll build
```
Use this command to validate that the site builds cleanly before committing changes. The output mirrors what GitHub Pages will publish.

## Project Structure
Key directories and files:

- `_config.yml` — Global configuration for the Jekyll site (site metadata, theme, plugins).
- `Gemfile` — Ruby dependencies, including `github-pages`, `minima`, and `jekyll-feed`.
- `_posts/` — Markdown source files for dated blog posts. Filenames follow `YYYY-MM-DD-title.md`.
- `index.md` — Points the home page to the theme's `home` layout.
- `about.md` — Example standalone page using the `page` layout.
- `index.html` and `404.html` — Optional overrides for theme templates.

## Content Workflow
1. Create or edit Markdown files in `_posts/` for dated entries. Ensure each file has the required [front matter](https://jekyllrb.com/docs/front-matter/) block (layout, title, date, categories).
2. Add standalone pages (e.g., `/about`) by creating Markdown files at the repository root with `layout: page` and specifying titles or permalinks as needed.
3. Update `_config.yml` for site-wide settings such as the title, description, base URL, and social handles.
4. Preview the site locally (`bundle exec jekyll serve`) to confirm formatting and layout before pushing.

## Testing and Validation
Before opening a pull request:
- Run `bundle exec jekyll build` to ensure the site builds without errors.
- Optionally run `bundle exec jekyll serve` and manually review pages in a browser.
- Check for broken links, formatting issues, or console errors in the browser developer tools during manual testing.

## Contributing
1. Fork the repository and clone your fork.
2. Create a feature branch for your change:
   ```bash
   git checkout -b feature/my-change
   ```
3. Commit your updates with clear messages and open a pull request against the main repository.
4. Include screenshots for visual changes when applicable. **TODO:** Document the preferred screenshot workflow once Kevin confirms the tooling.

## Deployment
The site is intended to be served via GitHub Pages. Pushing to the default branch triggers GitHub Pages to rebuild the site using the `github-pages` gem configuration. **TODO:** Confirm the exact branch (`main`, `master`, or `gh-pages`) that is published.

## Troubleshooting
- **Bundler version mismatch**: If you receive warnings about Bundler versions, run `bundle update --bundler` or install the version requested in the error message.
- **Missing native extensions**: Ensure that your system has the necessary build tools (Xcode Command Line Tools on macOS, `build-essential` on Ubuntu, etc.).
- **Port conflicts**: If `jekyll serve` fails because port 4000 is in use, specify a different port: `bundle exec jekyll serve --port 4001`.

## TODO
- Confirm the Ruby version required for production parity.
- Document the exact GitHub Pages branch and build settings.
- Add guidance on screenshot tooling for visual diffs.
- Capture any additional custom build or deploy automation steps if they exist.
