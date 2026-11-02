# Mochiii documentation

Source of the Mochiii documentation site, built with [Mintlify](https://mintlify.com).
The site describes Mochiii **1.5.0**.

## Layout

- `docs.json` is the site's configuration and navigation.
- `*.mdx` pages are the published site.
- `SITEMAP.md` is the planned list of pages.
- `CLAIMS.md` lists each factual claim and where in the 1.5.0 source it was checked.
- `NEXT_RELEASE.md` lists changes made after 1.5.0, kept for later.
- `.mintignore` keeps the three working files above, and this README, off the site.
  They are still readable here on GitHub.

## Preview locally

With Node.js 19 or later:

```bash
npx mint dev
```

Then open http://localhost:3000.

To check for broken links:

```bash
npx mint broken-links
```
