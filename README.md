# Academic site — Sirui (Sherry) Cai

Live at **https://siruisherrycai.github.io**. Built on
[academicpages](https://github.com/academicpages/academicpages.github.io) (Jekyll).
Push to `main`; GitHub Pages rebuilds in about a minute.

## Local preview

```bash
export PATH="/opt/homebrew/opt/ruby/bin:/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"
export JEKYLL_NO_BUNDLER_REQUIRE=true
jekyll serve            # http://localhost:4000
```

## Content

| What | Where |
|---|---|
| Home | `_pages/about.md` |
| Papers | `_publications/*.md` — `category:` is `jobmarket`, `manuscripts`, or `workingpapers` |
| Courses | `_teaching/*.md` |
| Conferences | `_talks/*.md` |
| Nav, sidebar, site title | `_config.yml`, `_data/navigation.yml` |
| PDFs | `files/` |

## Two things to know

`noindex: true` in `_config.yml` keeps the site out of Google while leaving link-sharing
intact. Set it to `false` to become findable. Leave `robots.txt` permissive — see
`private/NOTES.md` for why.

`private/` is gitignored and excluded from the build. Nothing in it is ever uploaded.

Working notes, the CV build steps, and the to-do list are in `private/NOTES.md`.
