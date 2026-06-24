# shortliststr.com

The Short List — a curated landing page of vacation-rental (STR) software, personally vetted by Michelle Marquis.

Static single-page site (one self-contained `index.html`, no build step). Fonts load from Google Fonts; all images/logos are inlined as data URIs.

## Local preview

```bash
python3 -m http.server 4321
# then open http://localhost:4321
```

## Deploy — GitHub Pages

This repo is configured to deploy straight from the branch root (no Actions, no build):

1. Push to GitHub (see below).
2. Repo **Settings → Pages**:
   - **Source:** Deploy from a branch
   - **Branch:** `main`  ·  **Folder:** `/ (root)`
3. The `CNAME` file sets the custom domain to **shortliststr.com**. Under Settings → Pages → Custom domain it should auto-populate; tick **Enforce HTTPS** once the cert is issued (can take a few minutes).

### DNS (at your domain registrar)

Point `shortliststr.com` at GitHub Pages:

| Type  | Host / Name | Value |
|-------|-------------|-------|
| A     | `@`         | `185.199.108.153` |
| A     | `@`         | `185.199.109.153` |
| A     | `@`         | `185.199.110.153` |
| A     | `@`         | `185.199.111.153` |
| CNAME | `www`       | `<your-username>.github.io` |

DNS can take up to a few hours to propagate. After it resolves, GitHub issues the HTTPS certificate automatically.

## Files

- `index.html` — the entire site
- `CNAME` — custom domain for GitHub Pages
- `.nojekyll` — skip Jekyll processing
