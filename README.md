# Meghana Kumar — GitHub Pages portfolio

A zero-dependency HTML/CSS portfolio for GitHub Pages and [meghanakumar.com](https://meghanakumar.com). No build step, no framework, no JavaScript libraries.

## Repository structure

```
/
├── index.html                          # Homepage
├── projects/
│   ├── index.html                      # Projects archive
│   └── project-template/
│       └── index.html                  # Starter template for a case study
├── writing/
│   ├── index.html                      # Writing archive
│   └── article-template/
│       └── index.html                  # Starter template for an article
├── about/
│   └── index.html                      # About page
├── assets/
│   ├── css/
│   │   └── styles.css                  # Shared stylesheet
│   ├── images/                         # Photos, hero images
│   └── diagrams/                       # Architecture diagrams
├── 404.html                            # Custom not-found page
├── CNAME                               # Custom domain (meghanakumar.com)
├── .nojekyll                           # Disables Jekyll processing
└── README.md
```

All pages share the same header and footer. Shared blocks are marked with HTML comments so they stay easy to copy and synchronize:

```html
<!-- SITE HEADER START -->
...
<!-- SITE HEADER END -->

<!-- SITE FOOTER START -->
...
<!-- SITE FOOTER END -->
```

When you change navigation, the skip link, or footer text, update these blocks on **every page**.

## Preview locally

From the repository root:

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000).

All internal links use root-relative paths (`/projects/`, `/writing/`, etc.) so the site works at both `localhost:8000` and `meghanakumar.com`.

## Create a new project

1. Copy the template folder:
   ```bash
   cp -r projects/project-template projects/my-project-name
   ```
2. Open `projects/my-project-name/index.html` and replace every `[placeholder]` value:
   - `<title>` and `<meta name="description">`
   - System identifier, title, thesis, category, year, status, role
   - All section content (Overview through Future work)
   - GitHub and demo URLs in the links block
   - Related writing link
   - Previous/next project navigation
   - Table of contents anchors (if you rename section `id` attributes)
3. Add images or diagrams to `assets/images/` or `assets/diagrams/` and replace the placeholder `<div>` elements with `<img>` tags.
4. Add a row to `projects/index.html` pointing to `/projects/my-project-name/`.
5. Optionally add a row on the homepage (`index.html`) under Selected projects.

## Create a new article

1. Copy the template folder:
   ```bash
   cp -r writing/article-template writing/my-article-slug
   ```
2. Open `writing/my-article-slug/index.html` and replace every `[placeholder]` value:
   - `<title>` and `<meta name="description">`
   - Category, title, abstract, publication date, reading time
   - Related project link (or remove the block)
   - Article body content
   - References
   - Previous/next article navigation
3. Add a row to `writing/index.html` pointing to `/writing/my-article-slug/`.
4. Optionally add a row on the homepage (`index.html`) under the writing section.

## Placeholder links and metadata

Search the repository for `PLACEHOLDER` and `[replace me]` comments to find values that need updating before launch:

| Location | What to replace |
|---|---|
| `index.html` | Selected project/article rows, GitHub and LinkedIn URLs |
| `about/index.html` | Biography, focus areas, contact links |
| `projects/project-template/` | All case study content and external links |
| `writing/article-template/` | All article content and references |
| Every page header | Only if you change site name or navigation items |
| Every page footer | Copyright year or tagline |

## Typography

- **Instrument Serif** — display headings, page titles, project titles, article titles
- **Manrope** — navigation, body text, metadata, buttons, labels, footer

Both fonts load from Google Fonts via a single `@import` in `assets/css/styles.css`. Monospace is used only inside `<code>` and `<pre>` blocks.

## Publish through GitHub Pages

1. Push this repository to a GitHub repo named `<your-username>.github.io` (or connect a custom domain).
2. In GitHub, open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Choose branch `main` and folder `/ (root)`, then save.
5. Wait a few minutes and visit your site.

### Custom domain (meghanakumar.com)

The `CNAME` file already contains `meghanakumar.com`. At your domain registrar:

**Apex domain** — add four A records for host `@`:

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

**www subdomain** — add a CNAME record:

- Host: `www`
- Value: `<your-github-username>.github.io`

Then in **GitHub → Settings → Pages**, confirm the custom domain and enable **Enforce HTTPS** after DNS verification.

## CSS organization

`assets/css/styles.css` is organized into labeled sections:

1. Font imports
2. Design tokens
3. Reset and base styles
4. Typography
5. Layout utilities
6. Header and navigation
7. Hero
8. Project archive
9. Writing archive
10. Project case study
11. Article typography
12. About
13. Footer
14. Responsive rules
15. Accessibility and reduced motion

Design tokens are defined as CSS variables (`--color-bg`, `--font-display`, `--reading-width`, etc.) at the top of the file.

## Before public launch

- [ ] Replace all placeholder project and article content
- [ ] Update GitHub, LinkedIn, and email links
- [ ] Write the About page biography
- [ ] Add favicon and social preview image
- [ ] Verify all navigation links resolve correctly
- [ ] Test on desktop, tablet, and mobile viewports
