# David Degras — academic website

A small Jekyll site for David Degras. The repository intentionally contains
only the files needed to edit content, build the site, and publish with GitHub
Pages.

## Structure

```text
_config.yml              Site identity and deployment URL
_data/navigation.yml     Header navigation
_includes/               Four reusable HTML components
_layouts/                Home, page, and publication layouts
_pages/                  Main website pages
_publications/           One Markdown file per publication
assets/css/main.scss     Complete visual system
images/biophoto.png      Profile portrait
DESIGN.md                Design rules for future changes
```

## Local preview

```sh
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

Open `http://localhost:4000/`.

## Updating the site

- Edit the main sections in `_pages/`.
- Add a publication by copying one file in `_publications/`. Use a lowercase,
  hyphenated filename and an ISO date such as `2026-07-10`; the filename becomes
  the publication URL automatically.
- Make visual changes only in `assets/css/main.scss`.
- Never commit `_site/`; GitHub Pages generates it during deployment.

## Current test deployment

The test site is published from `Yiming-S/ddegras.github.io` at:

<https://yiming-s.github.io/ddegras.github.io/>

After transferring the repository to `ddegras`, update the three deployment
values near the top of `_config.yml`:

```yaml
url: "https://ddegras.github.io"
baseurl: ""
repository: "ddegras/ddegras.github.io"
```
