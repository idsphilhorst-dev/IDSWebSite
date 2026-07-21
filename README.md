# Integral Design Software website

Static single-page site for [integraldesignsoftware.com](https://integraldesignsoftware.com), hosted on GitHub Pages.

## Local preview

Open `index.html` in a browser, or serve the folder:

```bash
# Python
python -m http.server 8080

# Node
npx serve .
```

## Publish to GitHub Pages

Repo: [idsphilhorst-dev/IDSWebSite](https://github.com/idsphilhorst-dev/IDSWebSite)

1. Push to the `main` branch (already configured if you used the initial setup).
2. In the GitHub repo: **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Choose branch **main** and folder **/ (root)**, then save.
5. Wait a minute or two. The site will be available at:
   - `https://idsphilhorst-dev.github.io/IDSWebSite/`
   - and at the custom domain once DNS is set (see below).

## Custom domain (`integraldesignsoftware.com`)

This repo includes a `CNAME` file with `integraldesignsoftware.com`.

### DNS at your domain registrar

Point the apex domain (and optionally `www`) at GitHub Pages.

**Option A — A records for the apex domain**

Create A records for `@` (or `integraldesignsoftware.com`) pointing to:

| Type | Name | Value |
|------|------|-------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

**Option B — ALIAS / ANAME** (if your DNS host supports it)

Point `@` to `idsphilhorst-dev.github.io`.

**www (recommended)**

Add a CNAME:

| Type | Name | Value |
|------|------|-------|
| CNAME | `www` | `idsphilhorst-dev.github.io` |

Then in **Settings → Pages**, set the custom domain to `integraldesignsoftware.com` and enable **Enforce HTTPS** once the certificate is ready (can take up to 24 hours after DNS propagates).

### After cutover

Update or remove the old WordPress hosting / DNS so traffic goes only to GitHub Pages.

## Content notes

- Contact uses phone and email links (no server-side form).
- Online Stripe checkout from the old WordPress site is not included; payments are handled via support contact.
