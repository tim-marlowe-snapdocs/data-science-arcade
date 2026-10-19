# Data Science Arcade

A cabinet of self-contained, zero-dependency HTML teaching games — one data-science
concept each, built for a non-technical audience. Every game is a single `index.html`;
open it in any browser, no build step.

**Play it:** https://tim-marlowe-snapdocs.github.io/data-science-arcade/

## Games

| Cabinet | Concept | Path |
|---|---|---|
| The Angler's Dilemma | Precision vs. recall | [`the-anglers-dilemma/`](the-anglers-dilemma/) |
| Weather Forecaster | Overfitting & the bias–variance tradeoff | [`weather-forecaster/`](weather-forecaster/) |

Each game keeps its own color identity (the Angler's blue, the Forecaster's green) over
a shared arcade look — gold frame, Courier, pixel sprites — so the cabinets read as one
family but are easy to tell apart.

## Structure

```
data-science-arcade/
  index.html                 # arcade landing / cabinet-select
  the-anglers-dilemma/
    index.html               # the game
  weather-forecaster/
    index.html               # the game
```

The landing page links to each game with a relative path, so it works both locally
(open `index.html`) and on GitHub Pages.

## Editing & publishing

GitHub Pages serves the site from the root of `main`, so **merging to `main` publishes
automatically** (first build takes a minute). Work on branches, not directly on `main`:

```sh
git switch -c tweak-weather-theme   # new branch
# edit the relevant game's index.html, test by opening it locally in a browser
git commit -am "Adjust Weather Forecaster palette"
git push -u origin tweak-weather-theme
gh pr create --fill                 # open a PR
# merge the PR -> main -> site redeploys
```

To preview locally just open `index.html` — it needs no server.

## Adding a new game

1. Create a new folder with a single `index.html` (reuse the house-style chassis).
2. Add a cabinet card to the root `index.html` grid (copy an existing `.cab` block,
   give it its own accent color).
3. Open a PR; merging redeploys the whole arcade.

## Leaderboard

Weather Forecaster stores high scores in Supabase via the project's **anon public** key
(embedded in its `index.html`, RLS-protected — safe to ship). Nothing sensitive is stored.
