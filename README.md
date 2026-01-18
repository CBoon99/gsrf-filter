# GSRF-Filter (Static Site)

This repo is a static site for **Gradient-Stabilized Recursive Filtering (GSRF)**:

- `/index.html`: main landing page
- `/demo/index.html`: interactive demo (uses Chart.js from a CDN)
- `/thanks/index.html`: Netlify form success page
- `/papers/gsrf/*.pdf`: papers linked from the landing page

## Deployment

This site is ready to deploy as a plain static site (no build step).

### Netlify

- Publish directory: the repo root
- The contact form in `index.html` uses Netlify Forms (`data-netlify="true"`) and posts to `/thanks/`.

### Other static hosts (S3/Cloudflare Pages/GitHub Pages)

- Upload the whole repo root as the site root.
- Note: internal links use absolute paths like `/demo/` and `/papers/...`, which assumes you deploy at the domain root (not under a subpath).

## Local preview

Any static file server works, e.g.:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080/`.

