# Style by Claud

A zero-dependency static storefront for an Amazon-affiliate fashion page, deployed on GitHub Pages.

**Live:** https://vijaxx.github.io/stylebyclaud/

---

## What it is

Instagram and similar platforms allow exactly one link in a bio. That single link has to keep working while the catalogue behind it changes constantly.

This repo is that link. It's a single `index.html` — no build step, no framework, no runtime dependencies — serving a responsive grid of shoppable looks, each tagged with the `stylebyclaud-21` Amazon Associates ID so referrals attribute correctly.

## Why it's built this way

The storefront is **generated, not hand-edited.** A companion automation pipeline harvests products from Amazon India bestsellers, builds the creative for each look, and regenerates `index.html` with the new item appended — then commits. The commit history is the product log: `storefront: 13 looks` → `14 looks` → `15 looks` → `16 looks`.

That drove three constraints:

- **Single self-contained file.** A generator that rewrites one file cannot break a dependency tree or a build. Nothing to install, nothing to compile, nothing that can fail at deploy time.
- **Static hosting.** GitHub Pages serves it directly from `main` at zero cost, with no server to keep alive. `.nojekyll` disables Jekyll processing so the file is served exactly as written.
- **A permanent URL.** The bio link never changes even as the catalogue turns over completely.

## Stack

HTML, CSS, and vanilla JavaScript in one file. GitHub Pages for hosting. Amazon Associates for affiliate attribution.

## Scope

This is deliberately the *smallest* piece of a larger system — the published surface, not the machinery. The harvesting, creative generation, and posting automation that feed it live in a separate project. Judged on its own, it's a static page; its value is being the stable, publicly-addressable endpoint that the automation writes to.

---

**Kondani Vijay Vardhan** · [GitHub](https://github.com/vijaxx) · [LinkedIn](https://www.linkedin.com/in/kondani-vijay-vardhan-b2729035a/)
