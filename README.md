# Academic site — Sirui (Sherry) Cai

Built on [academicpages](https://github.com/academicpages/academicpages.github.io) (Jekyll /
Minimal Mistakes). All plugins are GitHub Pages–whitelisted, so pushing to `main` is enough —
no GitHub Actions needed.

## Where this stands

Live at **https://siruisherrycai.github.io** — unlisted (see Search engine visibility below).

Repo: https://github.com/siruisherrycai/siruisherrycai.github.io
Push to `main` and GitHub rebuilds in about a minute.

```bash
cd ~/Local/sirui-cai-site
export PATH="/opt/homebrew/opt/ruby/bin:/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"
export JEKYLL_NO_BUNDLER_REQUIRE=true    # skips the github-pages Gemfile locally
jekyll serve                             # http://localhost:4000
```

## Where content lives

| What | Where |
|---|---|
| Home page | `_pages/about.md` |
| Papers | `_publications/*.md` — one file each, `category:` is `jobmarket`, `manuscripts`, or `workingpapers` |
| Courses | `_teaching/*.md` |
| Conference talks | `_talks/*.md` |
| CV page | `_pages/cv.md` (pulls the lists above in automatically) |
| Sidebar, nav, site title | `_config.yml`, `_data/navigation.yml` |
| PDFs | `files/` |

Section headings on the Research page come from `publication_category` in `_config.yml`.

## Light / dark

Follows the visitor's OS setting by default, with a sun/moon toggle in the header that
persists via `localStorage`. This is built into academicpages (`assets/js/_main.js`) — no
custom code. Change the palette with `site_theme` in `_config.yml`: `default`, `air`,
`sunrise`, `mint`, `dirt`, or `contrast`. Each ships a light and a dark variant.

## Search engine visibility

`_config.yml` has a single switch:

```yaml
noindex: true     # true = invisible in Google; false = findable
```

While `true`, every page sends `<meta name="robots" content="noindex,nofollow">`. Link
sharing is completely unaffected — anyone you send the URL to sees the site normally.

`robots.txt` deliberately **allows** crawling even while unlisted. That looks backwards but
is correct: a crawler must be able to fetch a page to see its `noindex` tag. Blocking in
robots.txt hides that instruction, and if anyone links to the site Google can then index a
bare URL with no description — visible in search *and* broken-looking. Google documents this
directly: https://developers.google.com/search/docs/crawling-indexing/block-indexing

To go public: set `noindex: false`, commit, push. Google usually picks it up within days;
`https://search.google.com/search-console` speeds it up.

Two caveats worth knowing:

* `noindex` is honored by Google and Bing but is a request, not access control. Anyone with
  the link can read and forward the page. Nothing private should live here.
* Going from unlisted to public is easy. The reverse is slow — once Google has indexed a
  page, removing it takes days to weeks. So the safe order is: stay unlisted until the
  content is final, then flip once.

## What is and isn't uploaded

The repo is public, so everything tracked by git is world-readable.

**Published:** the content collections (`_pages`, `_publications`, `_teaching`, `_talks`,
`_data/navigation.yml`), `_config.yml`, `images/profile.jpg`, `files/Cai_CV.pdf`, and the
academicpages theme code (`_includes`, `_layouts`, `_sass`, `assets`).

**Never uploaded:** anything under `private/` — gitignored *and* excluded from the Jekyll
build. That is where the CV LaTeX source, drafts, and unreleased PDFs live. The
full-resolution headshot sits further out still, at `~/Local/photos/`.

Nothing leaves `private/` on its own. To publish something from it, copy it into `files/`
or `images/` deliberately.

## The CV

Source: `private/cv/cv.tex` (local only). Only the compiled PDF is published.

```bash
cd private/cv
export PATH="/Library/TeX/texbin:$PATH"
latexmk -pdf cv.tex
cp cv.pdf ../../files/Cai_CV.pdf     # this copy is tracked and goes live
```

`\showabstractstrue` near the top prints full abstracts (3 pages). Flip it to
`\showabstractsfalse` for a compact version when an application caps CV length.

## Open items

- [ ] Fill in the four placeholders at the top of `private/cv/cv.tex`
      (`\BurdenRatioQOne`, `\BurdenRatioQFive`, `\THBPctIncQOne`, `\THBPctIncQFive`).
      They print as `[X.X]` etc. until then. Same numbers are described qualitatively in
      `_publications/2026-04-01-distributional-burden.md`.
- [ ] Fill in and uncomment the References section at the bottom of `private/cv/cv.tex`.
- [ ] Confirm whether FMA (Tampa, Oct 14-17 2026) involves presenting a paper. Listed under
      Presentations as attendance only.
- [ ] Optional: teaching statement, sample syllabus, evaluation summary in `files/`.
- [ ] Optional: add the job market paper PDF as `files/Cai_JMP.pdf` and link it. Nothing
      links to it today; the site says "available upon request" by design.
- [ ] Before AREUEA in January: set `noindex: false` in `_config.yml`.

Deliberately omitted: Google Scholar and ORCID (blank in `_config.yml`, so those sidebar
icons stay hidden), the home address and phone number on the CV, and the full-resolution
headshot (kept outside the repo at `~/Local/photos/scai-headshot-full.jpg`).
