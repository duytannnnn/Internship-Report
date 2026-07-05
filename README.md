# Internship Report

A personal internship report site built with [Hugo](https://gohugo.io/) and the
[hugo-theme-learn](https://github.com/matcornic/hugo-theme-learn) theme —
styled like [workshop-sample.awsfcaj.com](https://workshop-sample.awsfcaj.com/).

The site is bilingual (English / Vietnamese) and organized into 7 sections:

1. **Worklog** — 12 weekly work logs (pulled from the `worklog-` repo)
2. **Proposal** — final capstone project proposal (pulled from the `proposal` repo)
3. **Blogs Posted** — placeholder, to be added later
4. **Events Participated** — AWS community/internal events (pulled from `Events-Participated`)
5. **Workshop** — full hands-on serverless AI invoice scanner workshop (pulled from
   `Serverless-AI-Invoice-Scanner`)
6. **Self-Assessment** — placeholder, to be added later
7. **Sharing and Feedback** — placeholder, to be added later

## Running locally

1. Install Hugo (extended version, v0.123+): https://gohugo.io/installation/
2. From this folder, run:
   ```bash
   hugo server
   ```
3. Open http://localhost:1313/ in your browser.

## Building

```bash
hugo --minify
```

The static site is generated into the `public/` folder.

## Deploying to GitHub Pages

A ready-to-use GitHub Actions workflow is included at
`.github/workflows/hugo.yml`. To use it:

1. Push this project to a GitHub repository.
2. In the repo, go to **Settings → Pages** and set **Source** to
   **GitHub Actions**.
3. Push to the `main` branch (or run the workflow manually) — the site will
   build and deploy automatically.

## Editing content

All content lives under `content/`. Each section has an `_index.en.md` and
`_index.vi.md` (or `index.en.md` / `index.vi.md` for individual pages) so you
can edit the English and Vietnamese versions independently.

To finish the report:
- Add your blog posts under `content/3-blog/`
- Add your self-assessment under `content/6-self-assessment/`
- Add sharing & feedback content under `content/7-sharing-feedback/`

Update the author/company/duration details on the home page
(`content/_index.en.md` and `content/_index.vi.md`) to match your own info.

## Theme customization

Colors and other visual variables can be tweaked in
`themes/hugo-theme-learn/static/css/theme-blue.css`, or by switching the
`themeVariant` value in `hugo.toml` to `red`, `green`, or `blue`.
