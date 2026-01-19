# GSRF Filter (Gradient‑Stabilized Recursive Filtering)

**GSRF (Gradient‑Stabilized Recursive Filtering)** is a deterministic safety layer for recursive/feedback‑driven systems. It is designed to **bound update dynamics** so small deviations do not amplify into runaway behavior under recursion, and to make “stay within envelope” behavior visible and testable.

## Why it exists

Recursive systems (control loops, optimization engines, autonomous agents, decision pipelines) have a structural failure mode: **feedback amplification**. When outputs feed inputs, errors can compound across iterations, and probabilistic monitoring often triggers too late. GSRF focuses on deterministic bounding mechanisms intended to prevent runaway recursion paths rather than merely detecting them.

## Demo (fastest way to understand)

- Live demo: `https://gsrf-filter.netlify.app/demo/`
- Homepage: `https://gsrf-filter.netlify.app/`

The demo compares bounded (GSRF) versus unbounded (EMA) filtering on synthetic signals and surfaces overshoot + band‑crossing metrics.

## Run locally (no build tools)

This is a plain static site. Serve the repo root:

```bash
python3 -m http.server 8080
```

Then open:

- `http://localhost:8080/` (homepage)
- `http://localhost:8080/demo/` (demo)

### Hosting note (GitHub Pages project sites)

If you deploy as a GitHub Pages **project site** (served under `/<repo-name>/`), root‑absolute paths like `/demo/` break.
This repo uses **relative internal links** (e.g. `./demo/`, `./papers/...`) so it works on both project‑sites and root‑domain hosts.

Netlify Forms only runs on Netlify; other hosts will not process the form submission.

## Papers

PDFs are under `./papers/gsrf/` and linked from the site:

- Framework: `./papers/gsrf/gradient-stabilized-recursive-filtering-safety-critical-applications.pdf`
- Safety filter spec: `./papers/gsrf/gsrf-safety-filter.pdf`
- Safety brake overview: `./papers/gsrf/gsrf-safety-brake.pdf`

Abstract pages (HTML):

- `./paper-gsrf-framework.html`
- `./paper-gsrf-safety-filter.html`
- `./paper-gsrf-safety-brake.html`

## Commercial licensing (important)

This repo is licensed under **BSL 1.1** (see `LICENSE` and `LICENSE-NOTICE.md`).

- **Non‑commercial evaluation/research use is allowed.**
- **Commercial or production use requires a separate commercial license.**
- You may not offer it as a **service** (SaaS/hosted/managed offering) without a commercial license.

To discuss commercial licensing:

- Email: `info@boonmind.io`

## Patent status

**Patent application in preparation.**

## Cite this work

If you reference GSRF in academic or technical writing, you can cite the project as:

```text
Carl Boon. “GSRF Filter (Gradient‑Stabilized Recursive Filtering)”. https://gsrf-filter.netlify.app/ (accessed YYYY‑MM‑DD).
```

BibTeX:

```bibtex
@misc{boon_gsrf_filter,
  author       = {Carl Boon},
  title        = {GSRF Filter (Gradient-Stabilized Recursive Filtering)},
  howpublished = {\\url{https://gsrf-filter.netlify.app/}},
  note         = {Accessed: YYYY-MM-DD}
}
```

## Disclaimer

The demo is synthetic and is intended to build intuition. GSRF is not a certification claim, and it is not a guarantee of safety for all systems. You are responsible for validating suitability, bounds, and integration for your specific application.

