# Meghana Kumar — GitHub Pages portfolio

A zero-dependency HTML/CSS portfolio prepared for GitHub Pages and `meghanakumar.com`.

## Publish as your GitHub user site

1. Create a repository named exactly `<your-github-username>.github.io`.
2. Unzip this package.
3. Upload **the files inside this folder** to the repository root. `index.html` must be at the root, not inside another folder.
4. In GitHub, open **Settings → Pages**.
5. Under **Build and deployment**, select **Deploy from a branch**.
6. Select branch `main` and folder `/ (root)`, then save.
7. Wait a few minutes and open `https://<your-github-username>.github.io`.

## Connect meghanakumar.com

This package already contains a `CNAME` file with `meghanakumar.com`.

At your domain registrar, configure:

### Apex domain
Add these four A records for host `@`:

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

### www subdomain
Add a CNAME record:

- Host: `www`
- Value: `<your-github-username>.github.io`

Then in **GitHub → Settings → Pages**, confirm the custom domain is `meghanakumar.com` and enable **Enforce HTTPS** after DNS verification succeeds.

## Preview locally

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Edit

- Homepage: `index.html`
- Projects: `projects/index.html`
- Writing: `writing/index.html`
- About: `about/index.html`
- Styling: `assets/styles.css`

## Replace before public launch

- Placeholder project and article names
- GitHub and LinkedIn links
- About biography
- Favicon and social preview image
