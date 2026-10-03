# German Drills

Small, single-page browser games for drilling German grammar and vocabulary.
Each game is a self-contained HTML page (plus a `data.js` for the larger sets) — no build step, no dependencies beyond a couple of
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
- **[DerDieDas](derdiedas/)** — noun gender, tap der / die / das. 724 nouns,
  each with its plural, two or three example sentences (two random ones are
  shown at reveal) and, where one applies, a gender-pattern hint (suffix rules,
  compounds, nominalisations, natural-gender groups, named exceptions).
  Filters: level (A2/B1/B2/C1), pattern type, session length (10–100 or all).
- **[Rektion](rektion/)** — government of verbs, nouns, adjectives and
  case-only verbs. 559 items; pick "auf + Akk." style options (decoys include
  wrong-case variants of two-way prepositions and typical English/Russian
  interference errors). The reveal gives the filled sentence, the pronominal
  adverb (darauf) and the question form (Worauf?), notes for contrasts.
- **[VerbCombo](verbcombo/)** — Funktionsverbgefüge and fixed noun-verb pairs in
  two taps: the verb for the noun phrase, then the plain-verb equivalent. 449
  phrases with 2–3 examples for the phrase and 1–2 for the plain verb;
  alternative correct answers are accepted and shown.
- **[Teekesselchen](teekesselchen/)** — two modes: *lookalikes* (gap sentence,
  2–4 confusable words; 290 sets) and *homonyms* (one spelling, several
  meanings, chosen by context; 230 sets, with article and plural per meaning —
  a 2-meaning card is a plain two-way choice, no decoy).

All four share the Stammformen/Verbnester look and conventions: no typing
(everything is option-powered), an "Ich weiß es nicht 😢" button on every open
question, level checkboxes (A2/B1/B2/C1, all on by default) and session length
in the ⚙ panel, keyboard shortcuts (number keys select, 0 / ? = don't know,
Enter / Space = next), dark mode, weak-item weighting across sessions
(`localStorage`, optional), and a "Fehler wiederholen" round after a session.

### Data volume (units per CEFR level)

| Game | A2 | B1 | B2 | C1 | Total |
| --- | ---: | ---: | ---: | ---: | ---: |
| DerDieDas (nouns) | 138 | 167 | 163 | 256 | 724 |
| Rektion (items) | 93 | 128 | 166 | 172 | 559 |
| VerbCombo (phrases) | 65 | 126 | 146 | 112 | 449 |
| Teekesselchen (sets) | 102 | 117 | 159 | 142 | 520 |

Levels are tagged by the hardest sense/word in an item and were not inflated to
hit a quota: genuine A2 Funktionsverbgefüge (VerbCombo) and A2 case-government
items (Rektion) are scarce, which is why those two A2 columns stay below 100.

### How the German content was checked

Each data set was drafted in themed batches by AI authors and then audited twice
by separate AI reviewers (a second, stronger model for the second round) against
the same checklist — no human native-speaker proofreading yet: gender/plural/case endings, government and
collocations, spelling, example naturalness and factual accuracy, English
translations and — most important for the drills — that every wrong option
(decoy) is really wrong and that exactly one answer fits each gap. Both rounds changed a large share of the entries (in some files more than
half — mostly decoys and rule wordings) and deleted entries that could not be
made certain. This is a learner resource, not a dictionary:
if you spot a mistake, please open an issue.

## Adding a new game

1. Create a new folder at the repo root, e.g. `mein-spiel/`.
2. Put a single self-contained `index.html` in it (inline CSS/JS, only
   Google Fonts as an external dependency). Split out a `data.js` if the
   dataset is large, as Verbnester does.
3. Add a card for it to the root `index.html` and a bullet to this README.
4. Push to `main` — GitHub Pages redeploys automatically.
