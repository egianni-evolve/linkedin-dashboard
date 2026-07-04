# LinkedIn Insights Dashboard

A single-page dashboard that visualizes audience and growth analytics for Erika Gianni's LinkedIn presence. Published as a static site on GitHub Pages. No build step, no backend.

## What it shows

Derived from a complete LinkedIn data export (current data: Jul 3, 2026): network composition, audience shift over time, seniority and function breakdowns, top companies and industries, reaction and comment activity, and the correlation between posting and new connections (r = 0.61). Headline findings: a senior, decision-maker-heavy network (39% hold a formal Director/VP/C-suite title, 52% including founders), with AI and Legal the fastest-growing segments, and inbound connection requests now outpacing outbound.

## How it works

```
LinkedIn data export (CSVs)  →  analyze.py  →  metrics  →  hardcoded into index.html
```

- **`index.html`** is the entire dashboard: markup, styles, data arrays, and charts (Chart.js) in one file.
- **`analyze.py`** independently re-derives every metric from the raw LinkedIn CSV export using a documented keyword-based classification ruleset (roughly 75-85% accurate on titles). Its output is written to `analysis_output.json` (git-ignored).
- The computed numbers are copied into the data arrays in `index.html`. The dashboard itself does no live computation, which keeps it deterministic and reproducible across reviews.
- **`make_playbook_docx.py`** generates the companion CRAFT playbook document.

## Local development

No install or build step. Open `index.html` directly in a browser, or serve the folder:

```bash
python -m http.server 8000   # then open http://localhost:8000
```

## Refreshing the data

1. Drop in a new LinkedIn data export.
2. Re-run `python analyze.py`.
3. Update the data arrays in `index.html` with the new numbers.
4. Commit and push. GitHub Pages redeploys automatically.

## Deployment

Hosted on GitHub Pages, served directly from the repository. Pushing to the published branch redeploys the site.

## Notes

- Single-file by design. Project context and session history live in `SESSION.md`; change history in `CHANGELOG.md`.
- Classification is keyword-based and approximate. The "About These Numbers" note in the dashboard documents the methodology and its limits.