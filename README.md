# Hunchex — temporary landing page

A single static page shown while the Hunchex app is in development. Plain HTML, no runtime,
no build step, no forms, no cookies, no tracking. Published with GitHub Pages.

## Preview

```bash
python3 -m http.server 8080
```

Open `http://127.0.0.1:8080/`.

## Publishing (GitHub Pages)

Settings → Pages → Source: **Deploy from a branch**, branch `main`, folder `/ (root)`.
`.nojekyll` keeps Pages from running Jekyll over the files.

Custom domain: add a `CNAME` file containing the domain (e.g. `hunchex.com`), point DNS at
GitHub Pages (apex `A`/`AAAA` records or a `CNAME` to `<owner>.github.io` for a subdomain),
then tick **Enforce HTTPS**.

## Design assets

`assets/tokens.css`, `assets/mark.svg` and `assets/favicon.svg` are **copies** from the app
repository, where the design tokens live (`design/tokens/*.json` →
`python design/build_tokens.py` → `static/css/tokens.css`, `static/img/favicon.svg`). Never
edit them here: when the palette or the mark changes, copy the regenerated files again:

```bash
cp ../app/static/css/tokens.css ../app/static/img/mark.svg ../app/static/img/favicon.svg assets/
```

## Words

Same rules as the product: forecast, points; never bet, stake, wager, odds, bookmaker,
gambling, win money, demo.

## Removal

When the app is deployed on the domain, switch DNS to the app and archive this repository.
