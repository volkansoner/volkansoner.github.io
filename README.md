# volkansoner.github.io

Source of the academic website of Volkan Soner Özsoy, published with GitHub Pages at
<https://volkansoner.github.io>. It is a plain static site (HTML, Bootstrap 4, jQuery) with no build step.

## Structure

| Path | Purpose |
| --- | --- |
| `index.html` | Home page |
| `publications.html` | Journal articles (accordion with abstracts) |
| `citations.html` | Works citing the publications; each "Cited by" list is loaded from `citations/*.html` |
| `proceedings.html` | Conference proceedings |
| `teaching.html` | Courses |
| `citations/` | One HTML fragment per publication, fetched into `citations.html` with `fetch()` |
| `css/`, `js/`, `fonts/` | Bootstrap 4.6.2, jQuery 3.7.1, Academicons and `custom.css` |
| `files/` | CV and images |
| `robots.txt`, `sitemap.xml` | Search engine hints |

## Editing

- The navigation bar is repeated in each page. If you add a page, copy the `<nav>` block and update the `active` item,
  then add the page to `sitemap.xml`.
- To add a citation list, create `citations/<Name>.html` containing an `<ol reversed>` of `<li>` entries, then add a
  `<div id="collapse..." class="collapse" data-include="citations/<Name>.html">` in `citations.html`.
- Preview locally with `python3 -m http.server` and open <http://localhost:8000>. Opening the files directly with
  `file://` will not load the citation lists because browsers block `fetch()` there.
- A GitHub Action (`.github/workflows/check-links.yml`) checks that local file references exist.

## Third-party components

Bootstrap (MIT), jQuery (MIT), [Academicons](https://jpswalsh.github.io/academicons/) (font: SIL OFL 1.1, CSS: MIT)
and a Font Awesome kit loaded from its CDN. Their licenses apply to those files. The site content (texts, publication
list, CV) is the author's own; no license is granted for reuse unless stated otherwise.
