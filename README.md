# Blogs

Personal blog on software engineering, advertising technology, and data. Static site built with Jekyll 4, hosted on GitHub Pages.

**Live:** https://risyandi.github.io/blogs

## Stack

| Component | Detail |
|---|---|
| Generator | Jekyll `~> 4.4` |
| Runtime | Ruby >= 2.7 (3.3 recommended) |
| Styles | Sass with vendored Bourbon / Neat / Bitters (legacy syntax; deprecations silenced via `sass.silence_deprecations` in `_config.yml`) |
| Plugins | `jekyll-seo-tag`, `jekyll-sitemap`, `jekyll-paginate`, `jemoji` |
| Comments | Disqus (`disqus_shortname`) |
| Analytics | Google Analytics (legacy UA) |
| Frontend assets | Font Awesome 4.7, highlight.js, lightbox2 (all CDN) |

## Getting started

```bash
bundle install
bundle exec jekyll serve
```

Open http://localhost:4000/blogs/

## Project layout

| Path | Purpose |
|---|---|
| `_posts/` | Blog articles (Markdown) |
| `_layouts/` | Page templates: `default`, `page`, `post` |
| `_includes/` | Partials: `head`, `header`, `footer`, media embeds |
| `_sass/` | Styles: `base/` (variables, typography, buttons, forms), `_layout.scss`, vendored `bourbon/` + `neat/` |
| `_talks/` | Talks collection |
| `assets/` | Images, icons (`assets/icons/` holds favicon set + cactus logo) |
| `css/main.scss` | Sass entry point |

## Configuration

`_config.yml` is the source of truth — edit there, not in templates.

- Site metadata: `title`, `subtitle`, `description`, `url`, `baseurl`
- SEO / social cards: `protocols.fb_image`, `protocols.twitter_image` (og:image / twitter:image fallbacks)
- Integrations: `disqus_shortname`, `ga_tracking_id`, `social[]`
- Navigation: any page with `title` appears in the menu; opt out with `main_nav: false`
- Pagination: `paginate: 5`, path `/page:num/`

## Writing posts

File convention: `_posts/YYYY-MM-DD-slug.md`. Permalink is `:title`.

Front matter:

```yaml
---
title: Post Title
date: 2017-06-25
categories: [go, tooling]
cover: /assets/some-image.jpg   # optional
---
```

Posts without `cover` render the default header card (cactus logo on white). Social/Disqus card images fall back to `assets/cactus-card.png` (612x605).

## Deployment

Pushes to `master` are built by GitHub Actions (`.github/workflows/main.yml`) and deployed to the `gh-pages` branch. No manual build step.

## Design tokens

Palette follows the cactus `classic` scheme (see `_sass/base/_variables.scss`):

| Token | Value | Usage |
|---|---|---|
| Background | `#fafafa` | Body |
| Text | `#22272a` | Body copy |
| Meta | `#666` | Dates, secondary info |
| Link | `#567c77` | Links, buttons, header/footer blocks |
| Accent | `#cc2a41` | Titles (`h1`), nav menu, blockquote border, homepage post titles |

## License

MIT — see [LICENSE](LICENSE).
