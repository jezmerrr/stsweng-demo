# stsweng-devops-demo

Class demo for a GitHub Actions → GitHub Pages CI/CD pipeline.

## What it is

A static website (HTML / CSS / vanilla JS) that is automatically tested, built,
and deployed to GitHub Pages on every push to `main`.

## Structure

```
index.html              Landing page + links to all subpages
styles.css              Global styles
script.js               Button interaction demo
s02/ s03/ s06/          Student subpages
.github/workflows/      CI/CD pipeline (deploy.yml)
```

## Pipeline (`.github/workflows/deploy.yml`)

Triggered on push to `main` or manually (`workflow_dispatch`):

1. **build** – checks required files exist, copies the whole site into `_site/`
   (excluding `.git`, `.github`, and `README.md`), then uploads it as a Pages artifact.
2. **deploy** – publishes the artifact to the `github-pages` environment.

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```
