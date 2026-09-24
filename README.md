# German Drills

Small, single-page browser games for drilling German grammar. Each game is a
self-contained HTML file — no build step, no dependencies beyond a couple of
Google Fonts.

Play them at **https://alioshasemionov.github.io/german-drills/**

## Games

- **[Stammformen](stammformen/)** — drill the Präteritum, Partizip II, and
  auxiliary (hat/ist) of 388 German verbs (194 regular, 194 irregular).
  Typed answers with ä/ö/ü/ß-as-ASCII normalization, an "Ich weiß es nicht"
  reveal, verb-pool and session-length filters. Checking or revealing a card
  shows a Perfekt-tense example sentence (German + English) using that verb's
  exact aux/Partizip II forms.
- **[Verbnester](verbnester/)** — 50 stem-verb "nests" (steigen, werfen,
  stehen, nehmen, gehen, …) each with 3-9 prefixed derivatives whose meanings
  often have nothing obviously in common with the stem. Match each prefix to
  its row by tapping or dragging; the pool always includes 1-2 decoy prefixes
  so the last row can't be solved by elimination. Checking or revealing a
  round shows an example sentence per word (mixed tenses). Verb data lives in
  `verbnester/data.js`, separate from the game logic in `index.html`.

## Adding a new game

1. Create a new folder at the repo root, e.g. `mein-spiel/`.
2. Put a single self-contained `index.html` in it (inline CSS/JS, only
   Google Fonts as an external dependency). Split out a `data.js` if the
   dataset is large, as Verbnester does.
3. Add a card for it to the root `index.html` and a bullet to this README.
4. Push to `main` — GitHub Pages redeploys automatically.
