# jraugel.github.io

Personal website of **Joséphine Raugel**, built with [Astro](https://astro.build).

## Local dev

Requires Node 18+ (Astro's current floor is 20.9+ or 22+). The easiest way from
a Meta dev machine is:

```bash
source /public/apps/anaconda3/2023.03-1/etc/profile.d/conda.sh
conda activate nodejs   # this env was created with nodejs=22
npm install             # first time only
npm run dev             # dev server at http://localhost:4321/
```

Build static site:

```bash
npm run build   # outputs to dist/
npm run preview # preview the built site
```

## Deploying to GitHub Pages

This site is set up to deploy to **`jraugel.github.io`** (user site — served at
`https://jraugel.github.io/`).

### One-time setup

1. Create a new GitHub repo named exactly **`jraugel.github.io`** under your account.
2. Inside this folder:
   ```bash
   git init -b main
   git remote add origin git@github.com:jraugel/jraugel.github.io.git
   git add .
   git commit -m "Initial site"
   git push -u origin main
   ```
3. On GitHub, go to **Settings → Pages** and set **Source: GitHub Actions**.
4. Every push to `main` will re-deploy (`.github/workflows/deploy.yml`).

## Where to drop assets

See [`ASSETS.md`](./ASSETS.md) for the list of files to drop in `public/` so the
site renders with your real photo, logos, and paper videos. Until you do that,
the site uses placeholders.

## Structure

```
public/
  profile.jpg            ← your portrait (drop in)
  logos/
    meta.svg             ← provided
    ens.svg              ← provided (simple text mark; swap for official one)
  media/
    papers/<slug>.mp4    ← one video per paper (see ASSETS.md)
    talks/<slug>.{jpg,mp4}
src/
  layouts/Layout.astro
  components/
    Sidebar.astro        ← photo, bio side, socials
    PaperCard.astro      ← media-left / text-right card
  pages/index.astro      ← all content lives here
  styles/global.css
```

## Editing content

Everything shown on the page is defined in `src/pages/index.astro` in two
JavaScript arrays: `papers` and `talks`. Add/remove/edit entries there.
