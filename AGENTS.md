# Agent Instructions — Alessandro Suglia's Academic Website

## Project Overview

This is the personal academic website of **Dr. Alessandro Suglia**, Lecturer (Assistant Professor) at the School of Informatics, University of Edinburgh. It is built with [Hugo Blox Builder](https://hugoblox.com/) (Academic CV Starter theme) and deployed via Netlify.

## Build & Preview

```bash
# Build site (outputs to public/)
hugo --gc --minify

# Netlify production build (also runs pagefind for search indexing)
hugo --gc --minify -b $URL && npx pagefind --source 'public'
```

See [INSTALL.md](INSTALL.md) for Hugo v0.136.5 installation on macOS Apple Silicon.

## Content Architecture

| Path | Purpose |
|---|---|
| `content/authors/admin/_index.md` | Primary profile: bio, education, positions, skills, awards |
| `content/_index.md` | Homepage layout (biography, featured papers, recent papers) |
| `content/publication/` | 50+ publications, one folder per paper |
| `content/experience.md` | Resume page (pulls from author profile) |
| `content/teaching/` | Course pages (e.g., NLP, Python) |
| `content/esgi.md` | ESGI research group page |
| `config/_default/params.yaml` | Theme, SEO, appearance settings |
| `config/_default/menus.yaml` | Navigation menu |

## Content & Language Standards

### Academic Tone
- Use formal, precise academic English throughout. Avoid colloquial or marketing language.
- Prefer passive constructions and third-person references where appropriate (e.g., "This paper presents…" not "We show off…").
- Use field-standard terminology: *Embodied AI*, *Multimodal Learning*, *Conversational AI*, *Generative AI for Robotics*.

### Factual Accuracy — Critical
- **Never fabricate** publication titles, co-authors, venues, years, or DOIs. All publication data must come from the existing files in `content/publication/` or `publications.bib`.
- **Never invent** positions, affiliations, degrees, or awards not present in `content/authors/admin/_index.md`.
- When adding new publications, source data directly from DBLP or the official venue proceedings.
- Do not infer or extrapolate research claims beyond what is stated in the existing content.

## Publication Conventions

- **Folder naming:** `dblp-[type-shortname-authoryear]` (e.g., `dblp-confemnlp-suglia-0-bppekl-24`)
- **Date field:** Use `YYYY-01-01` for conference papers; exact date when known
- **Publication types:** `paper-conference` for conference papers; `article-journal` for journal articles
- **Featured papers:** Set `featured: true` to surface a paper in the homepage article-grid widget
- **Venue format:** Full venue name with location and dates in the `publication` field (e.g., `*Proceedings of EMNLP 2024, Miami, Florida, USA*`)

Example frontmatter:
```yaml
---
title: 'Paper Title in Single Quotes'
authors:
  - Alessandro Suglia
  - Co-Author Name
date: '2024-01-01'
publishDate: '2024-01-01T00:00:00Z'
publication_types:
  - paper-conference
publication: '*Full Venue Name, City, Country*'
doi: '10.18653/...'
links:
  - name: URL
    url: 'https://aclanthology.org/...'
featured: false
---
```

## Author Profile Conventions

- All positions, education, and awards live in `content/authors/admin/_index.md`.
- Date format for display: `Jan 2, 2006` (Hugo Go template format, configured in `params.yaml`).
- Profile fields follow Hugo Blox schema — do not add custom fields without checking the [Hugo Blox docs](https://docs.hugoblox.com/).

## Tags & Metadata

- Tags use title-case noun phrases (e.g., `Large Language Models`, `Generative AI`, `Embodied AI`).
- Do not add tags that misrepresent the research scope.
