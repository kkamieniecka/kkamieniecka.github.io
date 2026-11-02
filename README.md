# kkamieniecka.github.io

Personal academic website of Katarzyna Kamieniecka — built with [Quarto](https://quarto.org)
and published to GitHub Pages by GitHub Actions on every push to `main`.

Live site: <https://kkamieniecka.github.io>

## Keeping the identity graph in sync

`include/head.html` carries schema.org `Person` markup naming the ORCID iD
(0009-0004-2454-5950) and the Google Scholar profile. When you add another profile —
Scopus author page, ResearchGate, Wikidata, University of Bradford staff page — add its
URL to the `sameAs` array there and, where it makes sense, as a visible link too. Google
weighs crawlable links as well as the structured data.

Use the same photo (`assets/profile.jpg`) on every one of those profiles.

GitHub Pages builds from GitHub Actions, so pushes to `main` publish automatically.

## After it is live

- Verify the site in [Google Search Console](https://search.google.com/search-console)
  and submit `https://kkamieniecka.github.io/sitemap.xml`.
- Check the structured data with the
  [Rich Results Test](https://search.google.com/test/rich-results).
- Link back to this site from your Google Scholar profile, ORCID, LinkedIn, your
  University of Bradford staff page and your GitHub profile README. Links in both
  directions are what build the entity.

## Local preview

```bash
quarto preview        # live-reloading preview
quarto render         # one-off build into _site/
```

## Structure

| Path | What it is |
|---|---|
| `_quarto.yml` | site configuration, navbar, footer, theme |
| `index.qmd` | homepage |
| `research.qmd` | research themes |
| `software.qmd` | open-source tools |
| `publications.qmd` | publication list (generated from Crossref metadata) |
| `teaching.qmd` | training and teaching |
| `cv.qmd` | CV |
| `references.bib` | BibTeX for every publication listed |
| `include/head.html` | schema.org `Person` JSON-LD |
| `styles.scss` | theme overrides |
| `.github/workflows/publish.yml` | render + deploy to GitHub Pages |

## Adding a publication

Add an entry to `publications.qmd` following the existing `<div class="pub">` pattern,
and append the BibTeX record to `references.bib`. Crossref will give you both:

```bash
curl -s "https://api.crossref.org/works/<DOI>/transform/application/x-bibtex"
```
