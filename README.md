# Sunrise Realtor — Interactive Plot Layout

A single-page, self-contained interactive plot map for Sunrise Realtor.
Pan, zoom, search by plot number, and click any plot to see its area and
side dimensions. Works on desktop (mouse + scroll wheel) and mobile
(touch drag + pinch-zoom).

Everything — layout, styling, and logic — lives in `index.html`. There's
no build step and no dependencies; it's plain HTML/CSS/SVG/JS.

## Marking a plot as sold

Open `index.html` and search for:

```js
const soldPlotIds = [];
```

Add plot numbers (comma-separated) inside the brackets, then save and
refresh the page:

```js
const soldPlotIds = [4, 17, 25];
```

- **Numbered plots**: use the plain number, e.g. `4`
- **EB / LB**: use the quoted string, e.g. `"eb"`, `"lb"`
- **Park‑1**: use `"park-1"` (quoted, has a dash)
- **Park** (the large plot made of two path pieces) isn't supported by
  this list yet — flag it if you need it marked sold.

## Marking a plot as a corner site

Same pattern, a little further down:

```js
const cornerPlotIds = [];
```

Add the corner plot numbers the same way, e.g. `[4, 17, 31]`.

## Hosting on GitHub Pages

1. Push this repo to GitHub (see commands below).
2. On GitHub: go to **Settings → Pages**.
3. Under **Source**, choose the `main` branch and `/ (root)` folder, then
   **Save**.
4. GitHub gives you a live URL, usually:
   `https://<your-username>.github.io/<repo-name>/`
   (first deploy can take a minute or two).

Every time you edit `index.html` and push, the live site updates
automatically within a minute or so.

## Pushing to GitHub for the first time

```bash
git init
git add .
git commit -m "Initial commit: Sunrise Realtor plot map"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Replace `<your-username>` and `<repo-name>` with your GitHub username and
the repository name you created on GitHub.

## Updating the live site later

```bash
git add .
git commit -m "Mark plots 4, 17 as sold"
git push
```
