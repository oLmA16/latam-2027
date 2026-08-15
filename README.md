# LATAM Trip 2026/27 — Investigation Board

Interactive planning board for Berlin → Chile / Peru / Argentina, 5 Dec 2026 – 27 Jan 2027.
Single self-contained file: `index.html`. No build step, no dependencies to install.

**Live URL (after setup):** `https://<your-github-username>.github.io/latam-2027/`

---

## One-time setup (~5 minutes)

### Option 1 — Command line

```bash
cd "/Users/o.matten/Claude/Projects/LATAM Trip 2026:2027"

git init -b main
git add .
git commit -m "Initial board: three route versions"

# Create the repo and push. Needs the GitHub CLI (brew install gh; gh auth login).
gh repo create latam-2027 --public --source=. --push

# Turn on Pages, serving from the root of main
gh api -X POST repos/:owner/latam-2027/pages \
  -f "source[branch]=main" -f "source[path]=/"
```

Give it 1–2 minutes, then open `https://<your-username>.github.io/latam-2027/`.

If you'd rather not use `gh`, create an empty repo named `latam-2027` on github.com and then:

```bash
git remote add origin https://github.com/<your-username>/latam-2027.git
git push -u origin main
```

…then follow step 3 of Option 2 below.

### Option 2 — No terminal

1. Go to [github.com/new](https://github.com/new). Name it `latam-2027`, set it **Public**, don't add a README. Create.
2. On the empty repo page click **uploading an existing file** and drag in `index.html`, `robots.txt` and `README.md`. Commit.
3. **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save.**
4. Wait 1–2 min. The URL appears at the top of that same Pages settings page.

---

## Updating it later

The file lives in this folder. Claude edits `index.html` in place — you just publish:

```bash
cd "/Users/o.matten/Claude/Projects/LATAM Trip 2026:2027"
git add -A && git commit -m "Describe the change" && git push
```

GitHub Pages redeploys in ~30–60 seconds. **The URL never changes**, so the link you send your
partner keeps working forever and always shows the latest version.

No-terminal alternative: on the repo page, click `index.html` → pencil icon → paste the new
contents → Commit. Or use [GitHub Desktop](https://desktop.github.com/) and hit *Push origin*.

---

## Notes

- **Privacy.** A public repo means anyone with the URL can open the board. `robots.txt` and a
  `noindex` meta tag keep it out of search engines, but the URL itself isn't secret. That's
  usually fine for travel plans. If you want it genuinely private, GitHub Pages on a private
  repo requires GitHub Pro (~$4/month).
- **Version history is the real win here.** Every push is a snapshot, so you can compare or roll
  back if a version of the itinerary turns out to have been better three edits ago.
- **Internet required.** The board pulls map tiles from CARTO, the map library from unpkg,
  fonts from Google and photos from Wikimedia Commons. It won't render offline on the plane.
- **Mobile works** — the layout stacks the map above the dossier panel below ~1100px wide.

---

## What's in the board

Three route versions, each 51 nights on the ground, Dec 6 → Jan 26, with Christmas and New Year
in Temuco fixed in all three:

| | Version A · The Grand Loop | Version B · Right Season | Version C · Sea Level & Slow |
|---|---|---|---|
| Stops | 12 | 11 | 10 |
| Machu Picchu | yes | yes | no |
| Bariloche | yes | no | yes |
| Mendoza | yes | yes | no |
| Buenos Aires in | January | **December** | January |
| Highest sleeping altitude | 2,871 m | 2,871 m | **800 m** |
| Temuco block | 16 nights | **17 nights** | 17 nights |

Plus ~20 optional side trips ("leads") toggled from the header, and a Compare view laying out
the trade-offs.

### Things to verify before booking

- Saltos del Petrohué — reported Ruta 225-CH closure, July 2026
- PN Conguillío — reported open only as far as Truful-Truful
- Termas Los Pozones — reported closed since March 2026
- Volcán Villarrica alert level (SERNAGEOMIN) — governs PN Villarrica north sector access
- Machu Picchu 2027 ticket release window at tuboleto.cultura.pe
- Chilean rental car cross-border permit — request 5–10 working days ahead
