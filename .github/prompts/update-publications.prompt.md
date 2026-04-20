---
mode: agent
description: Fetches the latest publications from Alessandro Suglia's profile and creates missing publication entries in the Hugo site.
---

# Update Publications from DBLP

Your task is to synchronise the publications in `content/publication/` with the live DBLP profile.

## Step 0 — Determine the last-commit threshold date

Run the following command to obtain the date of the most recent git commit in this repository:

```bash
git log -1 --format=%cI
```

This returns an ISO-8601 timestamp (e.g., `2026-03-15T14:22:00+00:00`). Extract the **date portion** (`YYYY-MM-DD`) and treat it as the **threshold date**. Only papers whose publication date (year-month-day, or year alone when only the year is known) is **strictly after** this threshold date are eligible to be added.

If the git command fails, ask the user to supply the threshold date before continuing.

## Step 1 — Fetch the DBLP profile

Fetch the following URL and extract every paper entry (title, year, co-authors, venue if shown):

```
https://dblp.org/pid/184/4588.html
```

## Step 2 — Inventory existing publications

List all folder names under `content/publication/`. Each folder corresponds to one publication. Build a set of known paper titles by reading the `title:` field from each `content/publication/*/index.md` file.

## Step 3 — Identify new publications

A paper is eligible for addition only if **both** conditions hold:

1. Its publication date is **strictly after** the threshold date from Step 0. For papers where only the year is known, treat the date as `YYYY-01-01`; if the year alone is not after the threshold year, skip the paper.
2. No existing `content/publication/*/index.md` contains a matching title (case-insensitive, ignoring punctuation differences).

Do **not** create a duplicate entry if any close title match exists. Do **not** add papers published before or on the threshold date, even if they are missing from `content/publication/`.

## Step 4 — Retrieve full metadata for each new paper

For every new paper, fetch its DBLP page to obtain authoritative structured metadata. Search DBLP using the paper title:

```
https://dblp.org/search?q=<url-encoded-title>
```

Or fetch the DBLP record directly if the DBLP key is known. Use the DBLP data for:
- Exact title, authors, year
- Full venue name, location, and dates
- DOI and canonical URL

If the paper is a preprint (arXiv only), use the arXiv metadata page:
```
https://arxiv.org/abs/<arxiv-id>
```

> **Critical:** Never invent or guess author names, venue names, DOIs, or years. Only use data sourced from DBLP, the official venue proceedings, or arXiv.

## Step 5 — Determine folder name and publication type

**Folder naming convention:** `dblp-[type-shortname-authoryear]`
- Conference: `dblp-conf<venue>-<firstauthor>-<initials>-<yy>` (e.g., `dblp-confemnlp-suglia-0-bppekl-24`)
- Journal: `dblp-journals<venue>-<firstauthor>-<initials>-<yy>` (e.g., `dblp-journalsjair-suglia-kl-24`)
- Preprint / arXiv: `dblp-journalscorrabs-<arxiv-id-with-dashes>` (e.g., `dblp-journalscorrabs-2504-08590`)

If the DBLP key is available, derive the folder name directly from it.

**Publication type mapping:**
| Venue type | `publication_types` value |
|---|---|
| Conference / workshop proceedings | `paper-conference` |
| Journal article | `article-journal` |
| arXiv preprint | `article-journal` |


## Step 6 — Update `publications.bib`

Append the BibTeX entry for each new paper to `publications.bib`. Only append papers that passed the threshold filter in Step 3. Use the BibTeX from DBLP verbatim. For arXiv preprints, use the standard `@article` format with `journal = {arXiv preprint arXiv:XXXX.XXXXX}`.

## Step 8 — Report

After completing all additions, print a summary table:

| Folder created | Title | Venue | Year |
|---|---|---|---|
| … | … | … | … |

If any paper could not be added due to missing metadata, list it separately with the reason.
