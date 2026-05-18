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

Create a `Gemfile` in the repo root if one doesn't exist:

```ruby
source "https://rubygems.org"
gem "github-pages", group: :jekyll_plugins
```

Then install dependencies and start the dev server:

```bash
bundle install
bundle exec jekyll serve
```

The site will be available at http://localhost:4000. Jekyll watches for file changes and rebuilds automatically — refresh your browser to see updates.

> **Note:** The layout uses a custom `_layouts/default.html` and does not rely on the `minima` theme's templates, so the `theme: minima` line in `_config.yml` only pulls in Minima's default Sass variables. You can remove it safely if you don't need them.

## Deploy

Pushing to `main` triggers the GitHub Actions workflow in `.github/workflows/jekyll-gh-pages.yml`, which builds and deploys to GitHub Pages automatically. The custom domain `chadcyclingcoach.nxtlab.dev` is configured via the `CNAME` file.

## Editing content

- **Page copy, sections, and privacy policy** — edit `index.md`
- **Layout, navigation, styles, or the App Store link** — edit `_layouts/default.html`
- **Screenshots** — drop new PNGs into `assets/images/screenshots/` and reference them in the screenshot strip in `index.md`
- **Site metadata** (title, email, description) — edit `_config.yml`

