# Pattern Deck

A single-file, self-contained web app for practicing and tracking melodic
patterns/formulas transposed through tune harmony — built around a simple
loop: scan a hand-written pattern card, shuffle-pull cards to practice,
and log which tunes each pattern has "landed in."

Everything runs client-side. Cards, images, and landing logs are stored
locally in the browser (IndexedDB) — nothing is uploaded anywhere.

## Features

- **Add a card** — upload a photo or single-page PDF scan of a hand-written
  pattern card (e.g. exported from GoodNotes at A6 landscape). An optional
  back-scan can be added too.
- **Practice** — shuffle-pulls 1–2 random cards from the deck. Tap a card to
  flip between front/back. Mark **12 keys clean** and **showed up
  unprompted** as graduation criteria.
- **Landed in** — log which tune/spot each pattern has landed in, with an
  optional attached photo/PDF (chart excerpt, notes, etc. — multi-page PDFs
  are split page-by-page). A **×N / +1 / -1** tally tracks how many times
  you've reapplied the pattern to that same landing.
- **All cards** — browse every card, open full detail, delete.
- Every image opens full-size in a new browser tab (never downloads).

## Running it

This is a single HTML file with no build step and no server required.

- **Locally:** open `index.html` directly in a browser.
- **Hosted:** enable GitHub Pages for this repo (Settings → Pages → Deploy
  from branch → `main` / root) and it'll be live at
  `https://<username>.github.io/<repo>/`.

## `assets/pattern_card_template.pdf`

A printable index-card template (A6 landscape, matching GoodNotes' default
export size) with a ruled tab-notation area on the front and a ruled list
on the back. Import it into GoodNotes (or similar) as a page template, fill
one out per pattern with an Apple Pencil, export as a single-page PDF/photo,
and upload it to the app.

## Notes on storage

Card data (including embedded images) lives in the browser's IndexedDB,
scoped to whichever browser/device you're using — it does not sync between
devices or browsers. There's currently no export/import or backup feature.

## Tech

Single HTML file — vanilla JS, no build step. Uses
[pdf.js](https://mozilla.github.io/pdf.js/) (loaded from cdnjs) to render
PDF pages to images client-side.
