# CLAUDE.md

Guidance for Claude Code when working in this repository.

## Project

Personal portfolio website for **Ahmad Al-Hraki** — a single-page static site.

- **Live:** https://hraki1.github.io/portfolio/ (deployed via GitHub Pages)
- **Design:** Based on the [iPortfolio](https://bootstrapmade.com/iportfolio-bootstrap-portfolio-websites-template/) template by BootstrapMade.
- **Mockup / Wireframe:** Figma links are in [README.md](README.md).

## Stack & structure

There is **no build system, package manager, or framework** — it is hand-edited static files served as-is.

```
index.html            All page markup (single page, ~1000 lines, anchor-based sections)
assets/
  css/style.css       Main stylesheet (edit this for styling; all.min.css is a vendor bundle)
  js/main.js          All custom JS (nav, scroll, isotope filter, typed hero, contact form)
  img/                Images, profile photo, CV PDF, and portfolio/ screenshots
  vendor/             Third-party libs — DO NOT hand-edit
```

Vendor libraries in use: Bootstrap 5.3, AOS (scroll animations), Isotope (portfolio filtering),
GLightbox (lightbox), Swiper (sliders), Typed.js (hero typing effect), Waypoints (skill bars),
PureCounter (stat counters), Boxicons + Bootstrap Icons.

Page sections (anchors): `#hero`, `#about`, `#facts`, `#skills`, `#resume`, `#portfolio`, `#services`, `#contact`.

## Conventions

- Match the existing HTML style: 2-space indentation, double-quoted attributes, Bootstrap utility classes.
- Put custom styles in `assets/css/style.css` and custom behavior in `assets/js/main.js`. Never edit files under `assets/vendor/`.
- New scroll-animated elements use the `data-aos="..."` attribute (AOS is already initialized).
- The contact form has no backend — it builds a `mailto:` link to `ahmadhraki752@gmail.com` in `main.js`.
- Portfolio filtering keys off the `filter-*` classes on `.portfolio-item` elements combined with `data-filter` on `#portfolio-flters` buttons.

## Testing changes

No test suite. To verify a change, open `index.html` in a browser (or run a static server such as
`python -m http.server` from the repo root) and confirm the affected section renders and behaves correctly,
including at mobile widths.

## Deployment

Commit and push to `main`; GitHub Pages serves the site directly from the repo. No build step runs.

## Known issues worth fixing

- `index.html`: two social links use `lass="linkedin"` instead of `class="..."` (LinkedIn and GitHub icons).
- `<meta name="description">` and `<meta name="keywords">` are empty — bad for SEO/link previews.
