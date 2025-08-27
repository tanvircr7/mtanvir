# Minimal Quarto Site (GitHub Pages)

This is a Markdown-first personal site starter using **Quarto**. It’s minimal, easy to maintain, and free to host on GitHub Pages.

## 1) Install Quarto
- macOS (Homebrew): `brew install quarto`
- Windows/Linux: Download installers at <https://quarto.org/docs/get-started/>

## 2) Preview locally
```bash
quarto preview
```
It hot-reloads as you edit.

## 3) Push to GitHub
1. Create a new repo (recommend name: `personal-site`).
2. Replace placeholders in `_quarto.yml` and `index.qmd`:
   - `<your-github-username>`
   - `<your-repo-name>`
3. Initialize and push:
```bash
git init
git add .
git commit -m "Initial commit: Quarto site"
git branch -M main
git remote add origin https://github.com/<your-github-username>/<your-repo-name>.git
git push -u origin main
```

## 4) Enable GitHub Pages
The included GitHub Action publishes to the `gh-pages` branch on push to `main`.
- In your repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
- After a minute, your site should be live at:
  `https://<your-github-username>.github.io/<your-repo-name>/`

## 5) Everyday workflow
- New post: create a folder under `blog/posts/<slug>/index.qmd`.
- Edit nav/branding/colors in `_quarto.yml` and `styles.css`.
- Commit & push -> Action deploys automatically.

## Custom domain (optional)
- Add a `CNAME` file at repo root with your domain, e.g. `example.com`.
- Point DNS to GitHub Pages per the docs.

## Notes
- If you prefer manual deploys, you can run `quarto publish gh-pages` locally instead of using the Action.
- To add RSS, create `blog/_metadata.yml` with `feed: true`.

## Dark mode
Configured via `_quarto.yml` using a light + dark theme pair. Quarto auto-adds a theme toggle and remembers the user's preference.

## RSS feed
The blog listing (`blog/index.qmd`) has `feed: true`. Ensure `website.site-url` is set in `_quarto.yml` for correct feed links. The navbar includes an RSS icon linking to `blog/index.xml`.

## Taxonomy (categories)
`categories: true` enables filterable category chips in listings. A `Topics` page (`taxonomy/index.qmd`) lists all posts with category filters.
