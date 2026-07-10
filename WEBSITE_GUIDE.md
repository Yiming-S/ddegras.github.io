# David Degras-Valabregue Website — Content Guide

This guide explains how to update the website without changing its design or
technical structure. Routine content updates can be completed entirely in the
GitHub website; no local software is required.

During testing, the repository and website are:

- Repository: <https://github.com/Yiming-S/ddegras.github.io>
- Test website: <https://yiming-s.github.io/ddegras.github.io/>

After ownership is transferred, the repository will appear under the
`ddegras` GitHub account and the public address will become
`https://ddegras.github.io/`.

## 1. The standard editing workflow

1. Sign in to GitHub and open the website repository.
2. Open the file that contains the information you want to change.
3. Click the pencil icon labeled **Edit this file**.
4. Make the change and use the **Preview** tab to check the text.
5. Click **Commit changes**.
6. Write a short summary, for example `Add 2026 presentation` or
   `Update research description`.
7. For a routine text update, commit directly to `main`. The website will
   normally update within a few minutes.

GitHub keeps the complete history, so an earlier version can be recovered if a
mistake is made.

## 2. Where each part of the website is stored

| Website section | File or folder |
| --- | --- |
| Homepage and biography | `_pages/about.md` |
| Research | `_pages/research.md` |
| Publications page | `_pages/publications.md` |
| Individual publications | `_publications/` |
| Presentations | `_data/presentations.yml` |
| Software | `_pages/software.md` |
| Academic profile | `_pages/cv.md` |
| People directory | `_data/people.yml` |
| People page introduction | `_pages/people.md` |
| Teaching | `_pages/teaching.md` |
| Navigation menu | `_data/navigation.yml` |
| Presentation PDFs | `files/presentations/` |

For ordinary content updates, avoid editing `_config.yml`, `_layouts/`,
`_includes/`, or `assets/css/main.scss`. These files control deployment and
design.

## 3. Editing an existing text page

Open the relevant file in `_pages/`, click the pencil icon, and edit the text
below the second `---` line. Do not remove the block at the top of the file.

Basic Markdown formatting:

```markdown
## Section heading

Normal paragraph text.

- First item
- Second item

[Link text](https://example.com/)

**Bold text** and *italic text*
```

Use one blank line between paragraphs, headings, and lists.

## 4. Adding a publication

1. Open the `_publications/` folder.
2. Open a similar publication and copy its structure.
3. Choose **Add file → Create new file**.
4. Use a short lowercase filename with hyphens, for example
   `new-method-functional-data.md`.
5. Paste and complete this template:

```markdown
---
title: "Full paper title"
collection: publications
venue: "Journal or book title"
date: 2026-07-10
citation: "Author list, journal, volume, year, and pages."
---

### Abstract

Write or paste the abstract here.

[Publication record and DOI](https://doi.org/...)
```

Use the date format `YYYY-MM-DD`. The Publications page sorts entries
automatically, so no other file needs to be edited.

If an existing publication filename changes, preserve its old address with a
redirect:

```yaml
redirect_from:
  - "/publications/previous-address"
```

## 5. Adding a presentation

All presentation records are stored in `_data/presentations.yml`. The page
sorts them automatically by date, newest first.

For the first presentation, replace `presentations: []` with:

```yaml
presentations:
  - title: "Full presentation title"
    date: 2026-07-10
    type: "Invited talk"
    event: "Conference or seminar name"
    location: "Boston, MA"
    description: "One or two sentences describing the presentation."
    slides: "https://example.com/slides"
    video: "https://example.com/video"
    event_url: "https://example.com/event"
```

For later presentations, add another indented block beginning with `- title:`.
Keep the spacing exactly as shown. `description`, `slides`, `video`,
`event_url`, and `location` are optional; remove any unused line.

To host a PDF in the repository:

1. Open `files/presentations/`.
2. Choose **Add file → Upload files** and upload the PDF.
3. Use a lowercase filename with hyphens, such as
   `functional-data-seminar-2026.pdf`.
4. In `_data/presentations.yml`, use:

   ```yaml
   slides: "/files/presentations/functional-data-seminar-2026.pdf"
   ```

## 6. Adding software

Software entries are in `_pages/software.md`. Copy an existing
`<article class="software-card"> ... </article>` block, paste it before the
closing `</div>`, and update the project name, GitHub link, description, and
language label.

Use the next sequential number in the `software-index` line. For substantial
layout changes, ask the site maintainer rather than modifying the shared CSS.

## 7. Updating People, Teaching, or the academic profile

- **People:** add a record under `people:` in `_data/people.yml`. Copy an
  existing record and keep the same indentation:

  ```yaml
  - name: "Full name"
    category: "Graduate student"
    url: "https://profile-address.example/"
    status: "Academic status · Institution · Graduation date, if applicable"
    description: >-
      One concise sentence describing the person's research or work.
  ```

  The `description` field is optional and may be omitted for a minimal record.
  Edit the introductory paragraph separately in `_pages/people.md`.

- **Teaching:** keep evergreen course descriptions in `_pages/teaching.md`.
  Update them only when a course title or catalog description changes; link to
  the official catalog instead of adding semester or year headings.
- **Academic profile:** edit the corresponding section in `_pages/cv.md`. The
  public address remains `/cv/` so existing links continue to work. Keep dates
  and job titles consistent with the official university profile.

## 8. Updating the homepage

The homepage is `_pages/about.md`. It contains HTML because its layout is more
structured than the other pages. Simple wording and link changes are safe, but
do not delete opening or closing tags. Ask the site maintainer for layout,
portrait, color, typography, or spacing changes.

## 9. Checking the result

After committing a change:

1. Open the repository's **Actions** tab.
2. Wait for **pages build and deployment** to show a green check mark.
3. Open the website and visit the page you changed.
4. If the old version remains visible, refresh the page after a few minutes.
5. Test every new link and any uploaded PDF.

If a page displays `404`, first check the spelling and capitalization of the
filename or link. GitHub addresses are case-sensitive.

## 10. Before publishing content

- Confirm names, dates, titles, venues, and links.
- Publish only verified presentations and publications.
- Keep descriptions concise and factual.
- Do not upload private documents, student records, unpublished manuscripts,
  or files that do not have permission for public distribution.
- For a design or deployment change, contact the site maintainer before
  committing.
