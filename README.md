# Katherine Reads

A single-page site listing the 100 greatest books of all time, ranked — each with a cover, a one-line take, a tier grade (S–F), and a link to grab a copy. Static site, no build step.

## Files

- `index.html` — the whole site (HTML + CSS + a little vanilla JS).
- `books.js` — the data. **This is the only file you normally edit.**
- `vercel.json` — tells Vercel never to cache `books.js`, so your edits go live immediately.

## Editing the list

Open `books.js` and edit the `books` array. The file is just the data wrapped in
`window.KATHERINE_DATA = { … };` — keep that wrapper, and edit the entries inside.
(It's stored as `.js` rather than `.json` so the list also loads when you open
`index.html` directly from disk, not only when served over HTTP.) Each entry:

```js
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
- **Cover** — covers are served from the Penguin Random House cover CDN: `https://images.penguinrandomhouse.com/cover/<isbn>`. To change one, swap the ISBN in the URL (use the ISBN of the Penguin/PRH edition you want). You can also point `cover_url` at any other image URL.
- **Buy link** — `amazon_link` is currently an Amazon search URL. Swap for exact product or affiliate links later.

If the repo is connected to Vercel, every push to `main` redeploys automatically.

## Preview locally

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```
