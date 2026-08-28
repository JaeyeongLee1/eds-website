# EDSL Website Editing Rules

This repository powers the Engineering Data Science Lab website. Treat factual accuracy and preservation of the established design as hard constraints.

## General rules

1. Do not invent, infer, embellish, or rewrite factual content unless the user explicitly asks for wording changes.
2. Routine content updates belong in `_data/`. Do not edit page templates or CSS for a normal publication, member, alumni, award, editorship, education, or contact update.
3. Do not add marketing copy, slogans, claims, counts, rankings, venue categories, or research narratives that are not explicitly supplied.
4. Preserve spelling, capitalization, punctuation, affiliations, bibliographic details, and user-supplied typos unless explicitly asked to correct them.
5. Do not change the visual design unless explicitly requested. In particular, do not introduce cards, gradients, animations, blue row hover effects, decorative badges, or extra homepage sections.
6. Before modifying an existing GitHub file, fetch its current version and use its current blob SHA.

## Content files

- Professor facts: `_data/professor.yml`
- Current members: `_data/members.yml`
- Publications: `_data/publications/<year>.yml`
- Ph.D. alumni: `_data/alumni/phd.yml`
- M.S. alumni: `_data/alumni/ms.yml`

## Publications

Each year has one file such as `_data/publications/2026.yml` with a `year` field and an `items` list. Each publication item must contain:

- `code`
- `type`: `journal` or `conference`
- `title`
- `authors`
- `citation`: the complete bibliographic line shown below the paper
- `venue`: the separate right-side venue label

Keep year files in reverse chronological display order through their `year` value. Within a year, preserve the intended publication order. Do not shorten the `citation` field when a full bibliographic line is provided. Conference codes use `C`; journal codes use `J`.

For a publication in an existing year, edit that year's file. For a publication in a new year, create `_data/publications/<year>.yml` with the same schema.

## Members

Member records may contain:

- `name`
- `research_interests`
- `email`
- `entry`
- `homepage`
- `photo`

Do not fabricate a homepage, affiliation, email, research interest, or photograph.

## Alumni

Alumni records contain `year`, `name`, `thesis`, and `affiliation`. An empty affiliation is valid and must remain empty when no affiliation was supplied.

## Images

Repository-managed images belong under `assets/images/`. When a CMS-uploaded image path is stored as `/assets/images/...`, templates must render it through Jekyll's `relative_url` filter so the development GitHub Pages project URL and the final custom domain both work.

## Design intent

The site is intentionally restrained: white background, Helvetica/system sans-serif typography, precise grid, thin rules, black EDSL wordmark, and limited orange/blue semantic accents. The emphasis should remain on factual records and achievements rather than decorative copy.
