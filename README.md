# R.A.K.E — Electronic Press Kit

A minimal single-page EPK for the R.A.K.E solo project.

- `index.html` — the page
- `style.css` — styles (near-black, monospace, single column)
- `img/` — original photos + album cover
- `img/web/` — web-optimized copies the page actually loads

## Edit the content

Everything is hardcoded in `index.html`:

- **Bio / genre / fans-of** — the `<section class="bio">` block.
- **Release** — the Bandcamp embed + cover art in `<section class="release">`.
- **Video** — the YouTube id in `<section class="video">` (`.../embed/7OygssaJWYA`).
- **Photos** — the `<figure>` list in `<section class="gallery">`.
- **Contact** — the `mailto:` in the footer.

To add/replace a photo: drop the original in `img/`, then make a web copy:

```
sips -s format jpeg -s formatOptions 72 -Z 1400 img/NEW.JPG --out img/web/NEW.jpg
```

## Preview locally

```
cd rakeElectronicPressKit
python3 -m http.server 4178
```

Then open http://localhost:4178/

## Host on GitHub Pages

1. Create a new repo on GitHub (e.g. `rake-epk`), empty.
2. From this folder:

   ```
   git init
   git add .
   git commit -m "R.A.K.E EPK"
   git branch -M main
   git remote add origin git@github.com:YOUR_USERNAME/rake-epk.git
   git push -u origin main
   ```

3. On GitHub: **Settings → Pages → Source: Deploy from a branch → `main` / `root`**.
4. The site goes live at `https://YOUR_USERNAME.github.io/rake-epk/` within a minute or two.

`.nojekyll` is included so GitHub serves the files as-is.
