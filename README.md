# private-repo-page

**Deploy target — do not edit by hand.**

This repository hosts the **compiled** output of the React app whose source
lives in the private repository **`private-repo-cicd`**. It exists so the
source code can stay private while the built site is served by GitHub Pages.

## How it works

A GitHub Actions workflow in `private-repo-cicd` builds the app and force-pushes
the static files to the **`gh-pages`** branch of this repo using a short-lived
GitHub App token. The `main` branch holds only this note.

```
private-repo-cicd (source, private) ──build──▶ gh-pages branch here ──▶ GitHub Pages
```

## Pages configuration

- **Settings → Pages → Source:** *Deploy from a branch*
- **Branch:** `gh-pages` / `/ (root)`
- Served at: **https://kielchang.github.io/private-repo-page/**

To change the app, edit and push in **`private-repo-cicd`** — never commit to
the `gh-pages` branch here, as it is overwritten on every deploy.

See `SETUP.md` in `private-repo-cicd` for the one-time GitHub App setup.
