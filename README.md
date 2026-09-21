# routindo-web

The public **routindo.app** site — a landing placeholder plus the legal pages.
Plain static HTML, no build step, hosted on **GitHub Pages**.

```
index.html          → routindo.app/
privacy/index.html  → routindo.app/privacy
terms/index.html    → routindo.app/terms
fr/privacy/index.html → routindo.app/fr/privacy   (French)
fr/terms/index.html   → routindo.app/fr/terms     (French)
delete-account/index.html → routindo.app/delete-account
styles.css          → shared styles
CNAME               → custom domain (routindo.app)
.nojekyll           → serve files as-is (skip Jekyll)
```

> ⚠️ The Privacy Policy and Terms are **drafts** tailored to how the app works,
> and have them reviewed by a lawyer or a privacy-compliance tool **before**
> relying on them.

> ⚠️ **The French pages are not a certified translation.** They exist because
> Quebec's Bill 96 requires a fully equivalent French version of commercial web
> pages — explicitly including terms and privacy policies — and the app is
> distributed in Canada. They were translated carefully but not professionally,
> and a loose translation of a document people legally agree to is its own risk.
> Have them reviewed.

> **The four pages change together.** English and French are one document in two
> languages, so editing one and not the other is what the requirement exists to
> prevent — "fully equivalent" is the standard, and a French page a version
> behind is worse than an obvious gap. Re-stamp the "Last updated" / "Dernière
> mise à jour" date on both.

## Deploy (one-time)

1. **Create a repo** (e.g. `awwwdev/routindo-web`) and push these files to `main`.
2. **Enable Pages:** repo **Settings → Pages** → Source: `Deploy from a branch` →
   Branch: `main` / `/ (root)` → Save. Set **Custom domain** to `routindo.app`
   (this creates/uses the `CNAME` file) and tick **Enforce HTTPS** once available.
3. **DNS** at your registrar for the apex `routindo.app` — add GitHub Pages' four
   `A` records (see GitHub's "Managing a custom domain" docs; current values):
   ```
   A  @  185.199.108.153
   A  @  185.199.109.153
   A  @  185.199.110.153
   A  @  185.199.111.153
   ```
   Optionally add `CNAME  www  <user>.github.io` so `www` also works.
4. Wait for DNS to propagate; GitHub provisions a TLS certificate automatically
   (a few minutes to a few hours).

## Update

Edit the HTML directly and push — Pages redeploys automatically. Update the
"Last updated" date whenever the legal content changes.
