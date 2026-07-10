# David Degras — visual design system

This document is the source of truth for the visual language of the site. It
keeps future pages consistent with the French editorial mathematics direction.

## Direction

The site should feel like a contemporary French mathematics journal: quiet,
precise, warm, and readable. Use visual structure to clarify research rather
than to decorate it. Do not add audio, background video, gradients, generic
dashboard cards, or animated illustrations without a clear research purpose.

## Tokens

### Color

- `surface`: `#F4EFE7` — warm ivory page background
- `surface-raised`: `#FBF8F2` — paper panels and selected work
- `ink`: `#171B22` — headings and primary text
- `muted`: `#6D7072` — secondary text and captions
- `rule`: `rgba(23, 27, 34, .18)` — hairline dividers
- `cobalt`: `#244EB5` — primary links and research navigation
- `vermilion`: `#C94E36` — signal, active state, and emphasis
- `pale-yellow`: `#E9C967` — restrained highlight only
- `sage`: `#7DA18D` — rare supporting accent

Use cobalt for navigation and links, vermilion for emphasis, and pale yellow
or sage only as supporting marks. Never use all accents with equal weight in a
single component.

### Typography

- Display and section headings: Georgia or a high-contrast editorial serif,
  weight 400.
- Body and navigation: Arial or a neutral sans-serif.
- Eyebrows, years, and metadata: sans-serif, 10–12px, uppercase, tracking
  between `.12em` and `.16em`.
- Body copy: 16–18px with 1.55–1.7 line-height and a 62–72 character measure.

### Layout

- Maximum content width: `1120px`.
- Base spacing unit: `8px`.
- Section rhythm: `32px`, `48px`, `64px`, `96px`.
- Use hairline rules and open space instead of heavy cards and shadows.
- Prefer square or barely rounded surfaces; no pill-shaped UI unless it is a
  meaningful status marker.

## Components

- **Masthead:** name on the left; four primary destinations; People, Teaching,
  and Talks remain secondary.
- **Hero:** identity, role, one sentence of research positioning, and three
  direct actions. The visual should be a research map built from real topics.
- **Research chapter:** numbered editorial row with a question, method, and
  links to a paper or repository.
- **Publication record:** year rail, title, venue, short description, DOI or
  repository link.
- **Software record:** project name, one-line method description, language or
  application context, and repository link.
- **Footer:** GitHub, contact, Google Scholar, and Academia.

## Motion and accessibility

Motion is limited to short link and arrow transitions. Do not animate the page
continuously. Every interactive element needs a visible keyboard focus state.
Respect `prefers-reduced-motion: reduce` and preserve readable contrast on the
ivory surface.

## Responsive behavior

- At widths below `760px`, stack the hero and research map.
- Keep primary navigation compact; secondary links may wrap below it.
- Publication records remain one column with the year as a visible section
  heading.
- Research rows should never require horizontal scrolling.
