# Chad Public Site

Simple GitHub Pages site for the Chad app marketing page and public privacy policy.

Live at: https://chadcyclingcoach.nxtlab.dev

## File structure

- `index.md` — page content (hero, screenshots, features, privacy, privacy policy)
- `_layouts/default.html` — layout, CSS, and nav
- `_config.yml` — site title, email, description
- `assets/images/` — logo, favicon, and app screenshots
- `CNAME` — custom domain config for GitHub Pages

## Run locally

You need Ruby and Bundler. On macOS, Ruby ships with the OS but Bundler needs installing once:

```bash
gem install bundler
```

Then install dependencies and start the dev server:

```bash
bundle install
bundle exec jekyll serve
```

The site will be available at http://localhost:4000. Jekyll watches for file changes and rebuilds automatically — refresh your browser to see updates.

To verify the exact production build (what GitHub Pages will publish), build without a server and inspect `_site/`:

```bash
bundle exec jekyll build
```

> **Note:** The `Gemfile` pins `github-pages`, so the local build uses the same Jekyll version and plugins as the GitHub Pages deploy — if it builds locally, it builds on Pages.

## Mobile styling

The layout is mobile-first: single-column grids and a scrollable nav chip row on phones, expanding to two/three-column grids at 720px and 1080px. Key breakpoints and touch-target sizing (`--tap: 44px`) live in `_layouts/default.html`. Test mobile styling with your browser's device toolbar (e.g. Safari Web Inspector → Responsive Design Mode) against http://localhost:4000.

## Deploy

Pushing to `main` triggers the GitHub Actions workflow in `.github/workflows/jekyll-gh-pages.yml`, which builds and deploys to GitHub Pages automatically. The custom domain `chadcyclingcoach.nxtlab.dev` is configured via the `CNAME` file.

## Editing content

- **Page copy, sections, and privacy policy** — edit `index.md`
- **Layout, navigation, styles, or the App Store link** — edit `_layouts/default.html`
- **Screenshots** — drop new PNGs into `assets/images/screenshots/` and reference them in the screenshot strip in `index.md`
- **Site metadata** (title, email, description) — edit `_config.yml`

