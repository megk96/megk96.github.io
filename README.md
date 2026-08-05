# Meghana Kumar — GitHub Pages portfolio

A zero-dependency HTML/CSS portfolio for GitHub Pages and [meghanakumar.com](https://meghanakumar.com). No build step, no framework, no JavaScript libraries.

## Repository structure

```
/
├── index.html                          # Homepage
├── projects/
│   ├── index.html                      # Projects archive
│   └── policy-friction-intelligence-platform/
│       └── index.html                  # Project case study
├── writing/
│   ├── index.html                      # Writing archive
│   └── every-ai-architecture-mistake-we-made-in-2026/
│       └── index.html                  # Article
├── about/
│   └── index.html
├── templates/
│   ├── project-template.html           # Internal starter (not linked publicly)
│   └── article-template.html           # Internal starter (not linked publicly)
├── assets/
│   ├── css/styles.css
│   ├── images/
│   └── diagrams/
├── 404.html
├── CNAME
├── .nojekyll
└── README.md
```

Shared header and footer blocks are marked on every page:

```html
<!-- SITE HEADER START -->
...
<!-- SITE HEADER END -->

<!-- SITE FOOTER START -->
...
<!-- SITE FOOTER END -->
```

When navigation or footer text changes, update these blocks on every public page.

## Preview locally

```bash
python3 -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000). All links use root-relative paths (`/projects/`, `/writing/`, etc.).

## Create a new project

1. Copy the internal template into a new folder:
   ```bash
   mkdir -p projects/my-project-slug
   cp templates/project-template.html projects/my-project-slug/index.html
   ```
2. Edit `projects/my-project-slug/index.html` — replace instructional comments and placeholder content with your case study.
3. Add a row to `projects/index.html` linking to `/projects/my-project-slug/`.
4. Optionally feature it on `index.html` under Selected projects.

Only add GitHub or demo links when real URLs exist. Remove those blocks entirely otherwise.

## Create a new article

1. Copy the internal template into a new folder:
   ```bash
   mkdir -p writing/my-article-slug
   cp templates/article-template.html writing/my-article-slug/index.html
   ```
2. Edit `writing/my-article-slug/index.html` — set title, abstract, date, reading time, and body content.
3. Add a row to `writing/index.html` linking to `/writing/my-article-slug/`.
4. Optionally feature it on `index.html` under the writing section.

When multiple articles exist, uncomment the prev/next navigation block in the template.

## Publish through GitHub Pages

1. Push to a GitHub repo named `<your-username>.github.io` (or connect a custom domain).
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Choose branch `main` and folder `/ (root)`.
5. Wait a few minutes, then visit your site.

### Custom domain (meghanakumar.com)

The `CNAME` file contains `meghanakumar.com`. Configure DNS at your registrar:

**Apex domain** — four A records for `@`:

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

**www subdomain** — CNAME record:

- Host: `www`
- Value: `<your-github-username>.github.io`

Then enable **Enforce HTTPS** in GitHub Pages settings after DNS verification.

## Typography

- **Instrument Serif** — display headings, page titles, project titles, article titles
- **Manrope** — navigation, body text, metadata, buttons, labels, footer

Both load from Google Fonts via a single `@import` in `assets/css/styles.css`.
