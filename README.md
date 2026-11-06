# cmustatgen.github.io

Source for https://cmustatgen.github.io/ — the website of the CMU Statistical
Genomics group. Built with Jekyll 4 and deployed by GitHub Actions.

## Editing content

Everything the site shows lives in `_data/`:

| File | What it holds |
|------|---------------|
| `_data/people.yaml` | Every person, keyed by slug (name, position, affiliation, url, photo) |
| `_data/roster.yaml` | Who appears on `/people/`, grouped as faculty / member / alumni |
| `_data/terms.yaml` | Semesters, newest first; the first entry is the homepage schedule |
| `_data/talks/<term>.yaml` | One file per semester with the talks |

Photos go in `assets/people/` (320x400 px recommended; see
`scripts/optimize_images.py`).

## Local preview

```sh
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000/.

## Deploying

Push to `main`. The workflow in `.github/workflows/pages.yml` builds the site,
checks that every page renders and that colour tokens keep WCAG AA contrast,
then publishes to GitHub Pages. In the repository settings, set Pages →
Source to **GitHub Actions**.
