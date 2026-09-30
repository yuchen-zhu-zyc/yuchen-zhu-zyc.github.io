# Yuchen Zhu's website

Personal academic website built with Jekyll and the al-folio theme.

## Everyday updates

| What to update | File |
| --- | --- |
| Homepage introduction and profile | `_pages/about.md` |
| Publications, venues, links, and awards | `_bibliography/papers.bib` |
| News / Updates | `_data/news.yml` |
| Talks | `_data/talks.yml` |
| Coauthor links | `_data/coauthors.yml` |
| Publication topic labels and colors | `_data/keywords.yml` |
| Profile photo and institution logos | `assets/img/` |
| Publication thumbnails | `assets/img/publication_preview/` |
| Conference posters | `assets/pdf/` |

Put new news items at the top of `_data/news.yml`. Dates use `MM/YYYY`, and
`content` accepts HTML links and formatting.

The homepage's Selected Publications use the same bibliography as the full list.
Only entries with `selected={true}` appear there. Use `selected={false}` when
adding a paper only to the full publication list.

`_data/service.yml` and `_includes/service.html` contain the optional reviewer
service section; its inclusion is currently commented out in `_layouts/about.html`.

## Local preview

Use Ruby 3.2 or newer and Bundler, then run:

```sh
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 4000
```

Open <http://127.0.0.1:4000/> or <http://127.0.0.1:4000/publications/>.
Jekyll rebuilds when content files change. Restart the server after changing
`_config.yml`.

## Deployment

Pushing to `master` or `main` triggers `.github/workflows/deploy.yml`.
It builds the site in production mode, runs PurgeCSS, and publishes `_site/`
to the `gh-pages` branch for GitHub Pages.

Keep `.github/workflows/deploy.yml`, `Gemfile`, `_config.yml`, and
`purgecss.config.js` with the project. No Docker setup is required.

## Supporting directories

- `_layouts/` and `_includes/`: page structure and reusable components.
- `_sass/`, `assets/css/`, `assets/js/`, and the font directories: presentation
  and interactions. Some files also affect production CSS pruning, even when
  they are not loaded directly by a page.
- `_plugins/`: local Jekyll extensions.
- `vendor/` and `.bundle/`: local Ruby dependencies and Bundler settings;
  ignored by Git. Removing `vendor/` requires reinstalling dependencies.
- `_site/` and `.jekyll-cache/`: generated output and cache; ignored by Git.
  Do not edit `_site/` directly.

The `/blog/`, `/projects/`, and `/teaching/` pages remain available even though
they are not in the navigation. The blog currently includes the theme's sample
external feed. Keep them unless intentionally retiring those URLs.

The theme's license is preserved in `LICENSE`.
