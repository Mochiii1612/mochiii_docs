# Mochiii documentation

Source of the Mochiii documentation site, built with [Mintlify](https://mintlify.com).
The site describes terminal app **1.6.1** and VS Code extension **1.0.1**, which works
with terminal app 1.6.1 or later.

## Layout

- `docs.json` is the site's configuration, navigation and redirects.
- `*.mdx` pages are the published site; `images/screens/` holds their screenshots,
  all from real runs with a model on the author's computer.
- `SITEMAP.md` lists every page with the source files its facts come from.
- `.mintignore` keeps `SITEMAP.md`, and this README, off the site.
  They are still readable here on GitHub.

## Preview locally

With Node.js 18 or later:

```bash
npx mint dev
```

Then open http://localhost:3000.

To check for broken links:

```bash
npx mint broken-links
```
