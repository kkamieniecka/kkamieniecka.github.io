# kkamieniecka.github.io

Personal academic website of Katarzyna Kamieniecka — built with [Quarto](https://quarto.org)
and published to GitHub Pages by GitHub Actions on every push to `main`.

Live site: <https://kkamieniecka.github.io>

## Two things to do before this is finished

1. **Add your ORCID iD and Google Scholar ID** to the `sameAs` array in
   `include/head.html`. The file has instructions at the top. This is the single most
   important edit for search visibility: it is the machine-readable statement that all
   of your profiles belong to the same person.
2. **Use the same photo everywhere.** `assets/profile.jpg` is now your headshot; use the
   identical image on Google Scholar, LinkedIn and your University of Bradford staff
   page. Identical images across profiles is one of the signals Google uses to tie them
   to one person.

GitHub Pages is already configured to build from GitHub Actions, so pushes to `main`
publish automatically.

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
