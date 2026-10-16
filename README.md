# Palmares website

Static, buildless GitHub Pages site. No JavaScript application, cookies, analytics, tracking or external fonts. The look follows Palmares' Alpine '72 design system.

| Page | File | App Store Connect field |
|---|---|---|
| Marketing | `index.html` | Marketing URL |
| Support / FAQ | `support.html` | Support URL |
| Contact | `contact.html` | — |
| Privacy Policy | `privacy.html` | Privacy Policy URL |
| Terms | `terms.html` | — |
| Not found | `404.html` | — |

All internal links are relative. Canonical metadata, `robots.txt` and `sitemap.xml` use the final GitHub Pages address:

```text
https://palmares.github.io/
```

The publishing repository must therefore be named `palmares.github.io` under the `palmares` GitHub account.

## Local preview

From the repository root:

```sh
python3 -m http.server 8080 --directory site
```

Open `http://localhost:8080/` and verify Home, Support, Contact, Privacy, Terms and the 404 page at phone and desktop widths.

## GitHub Pages

Publish the contents of `site/` at the root of the dedicated public repository `palmares/palmares.github.io`. In that repository choose **Settings → Pages → Deploy from a branch → `main` → `/ (root)`**. `.nojekyll` prevents Jekyll processing.

After the public URL is live:

1. Verify `/`, `/support`, `/privacy` and `/terms`.
2. Update canonical, Open Graph, sitemap and robots URLs if the deployed base differs.
3. Confirm the Marketing, Support and Privacy Policy URL fields in every localized `appstore/*/app-store-listing.md` match the deployed pages.
4. Run `python3 Tools/asc/asc.py validate --require-complete`.

## Keeping it accurate

The privacy and support pages describe the current app: local saves, StoreKit, Game Center entitlement, no developer server, no analytics, no ads and no tracking SDKs. Update the pages and App Store privacy answers before adding iCloud, notifications, analytics, crash reporting, advertising, accounts or a backend.
