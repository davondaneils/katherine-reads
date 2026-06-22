# Katherine Reads

A single-page site listing the 100 greatest books of all time, ranked — each with a cover, a one-line take, a tier grade (S–F), and a link to grab a copy. Static site, no build step.

## Files

- `index.html` — the whole site (HTML + CSS + a little vanilla JS).
- `books.json` — the data. **This is the only file you normally edit.**
- `covers/` — locally-hosted cover images (everything else loads covers from Open Library).

## Editing the list

Open `books.json` and edit the `books` array. Each entry:

```json
{
  "rank": 1,
  "title": "Nineteen Eighty-Four",
  "author": "George Orwell",
  "tier": "D",
  "description": "A chilling vision of total surveillance…",
  "amazon_link": "https://www.amazon.com/s?k=…",
  "cover_url": "covers/1984.jpg"
}
```

- **Tier grade** — set `"tier"` to `S`, `A`, `B`, `C`, `D`, `E`, or `F`. Leave it `""` for an unranked book (shows a neutral dashed slot).
- **Cover** — point `cover_url` at any image URL, or drop a file in `covers/` and reference it (e.g. `covers/dune.jpg`).
- **Buy link** — `amazon_link` is currently an Amazon search URL. Swap for exact product or affiliate links later.

If the repo is connected to Vercel, every push to `main` redeploys automatically.

## Preview locally

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```
