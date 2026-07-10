# David Degras — academic website

Source for the academic website of David Degras, Associate Professor in the
Department of Mathematics at the University of Massachusetts Boston. The site
presents his research, publications, open-source software, teaching, and
academic profile in a small, maintainable Jekyll project.

**Current test site:** <https://yiming-s.github.io/ddegras.github.io/>

The repository is temporarily hosted by `Yiming-S` for testing. Ownership has
not yet been transferred to David Degras.

## Content sources

Biographical and research information should remain consistent with these
public profiles:

- [UMass Boston faculty profile](https://www.umb.edu/directory/daviddegras/)
- [Google Scholar](https://scholar.google.com/citations?user=CYLjVg4AAAAJ&hl=en)
- [GitHub](https://github.com/ddegras)
- [Academia](https://um-boston.academia.edu/DavidDegras)

## Repository map

```text
_config.yml              Identity, deployment URL, and Jekyll settings
_data/navigation.yml     Header navigation
_data/presentations.yml  Presentation records, sorted automatically
_includes/               Header, footer, metadata, and publication row
_layouts/                Home, standard page, and publication layouts
_pages/about.md           Homepage and primary biographical introduction
_pages/                   Main sections, including Presentations
_publications/            One Markdown file per publication
assets/css/main.scss      Entire visual system and responsive layout
files/presentations/      Optional presentation PDFs
images/biophoto.png      Profile portrait
DESIGN.md                Rules for the French editorial design direction
WEBSITE_GUIDE.md         Nontechnical content guide for the site owner
```

Generated output, theme vendors, JavaScript libraries, and unused demonstration
content are intentionally excluded.

## Common updates

### Homepage or biography

Edit `_pages/about.md`. This file is the homepage because its permalink is `/`.
Keep the introduction concise and verify professional details against the
public profiles above.

### Main pages and navigation

- Edit page content in `_pages/`.
- Edit header links in `_data/navigation.yml`.
- Keep internal links compatible with the project `baseurl` by using Jekyll's
  `relative_url` filter.

### Publications

Copy an existing file in `_publications/` and use a lowercase, hyphenated
filename. The filename becomes the publication URL automatically.

```yaml
---
title: "Paper title"
collection: publications
venue: "Journal title"
date: 2026-07-10
citation: "Authors, volume, year, and pages."
---

Short description or abstract.

[Publication record and DOI](https://doi.org/...)
```

Use an ISO date (`YYYY-MM-DD`) so the publication list sorts correctly. If an
existing filename or URL changes, add its previous path under `redirect_from`
so bookmarks and cached pages do not produce a 404.

### Presentations

Add verified talks, seminars, tutorials, or conference presentations in
`_data/presentations.yml`. The Presentations page sorts records automatically
and supports optional slide, video, and event links. The complete copy-and-paste
template is in `WEBSITE_GUIDE.md`.

Presentation PDFs may be uploaded to `files/presentations/` and linked with a
site-relative path such as `/files/presentations/talk-title-2026.pdf`.

### Design

Make visual changes in `assets/css/main.scss` and consult `DESIGN.md` before
adding new components. The site deliberately uses one stylesheet, no runtime
JavaScript, and no external theme layer.

## Local preview

The project uses Ruby 3.1.7 and the GitHub Pages dependency set.

```sh
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

Open <http://localhost:4000/>. Before publishing, run the production build:

```sh
bundle exec jekyll build --config _config.yml
```

Do not commit `_site/`; GitHub Pages generates it during deployment.

## Test deployment

GitHub Pages currently publishes the `main` branch from the repository root:

- Repository: <https://github.com/Yiming-S/ddegras.github.io>
- Website: <https://yiming-s.github.io/ddegras.github.io/>

The temporary deployment values are stored near the top of `_config.yml`.

## Ownership transfer checklist

After transferring the repository to the `ddegras` account:

1. Confirm the repository name is `ddegras.github.io`.
2. Update `_config.yml`:

   ```yaml
   url: "https://ddegras.github.io"
   baseurl: ""
   repository: "ddegras/ddegras.github.io"
   ```

3. In GitHub Pages settings, publish from `main` and the repository root.
4. Wait for the Pages deployment to complete, then test the homepage, main
   navigation, portrait, stylesheet, and several publication links.
5. Keep HTTPS enabled.

## Maintenance principles

- Preserve the quiet French editorial visual direction.
- Prefer typography, spacing, and content hierarchy over decorative effects.
- Do not add audio, background video, continuous animation, or generic widgets.
- Keep publication URLs stable and retain redirects when a URL must change.
- Add dependencies only when the content cannot be implemented cleanly with
  the existing Jekyll structure.

For step-by-step editing instructions written for the future site owner, see
[`WEBSITE_GUIDE.md`](WEBSITE_GUIDE.md).
