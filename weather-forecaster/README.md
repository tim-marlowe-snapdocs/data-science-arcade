# Weather Forecaster: Pick the Forecast

A self-contained, zero-dependency HTML teaching game about overfitting and the
bias–variance tradeoff, built for a non-technical audience. The entire game is
`index.html` — open it in any browser, no build step.

**Play it:** https://tim-marlowe-snapdocs.github.io/data-science-arcade/weather-forecaster/

Part of the [Data Science Arcade](../). See the [arcade README](../README.md) for the
branch/PR publish workflow.

Three forecasters each fit the same recorded week, then project the coming days:
Straight-Line Steve (a ruler), Trend-Spotter Tess (follows the real shape), and
Dr. Wiggles (threads every recorded dot). Pick who you trust for the days nobody has
seen yet. The curve that best explains the past is usually not the one that predicts
the future — that gap is the lesson.

## Editing

`index.html` is the single source of truth — edit it, then preview locally by opening
the file (`open index.html`); it needs no server. Merging to `main` redeploys the whole
arcade; see the [arcade README](../README.md) for the branch/PR workflow.

## Leaderboard

High scores are stored in Supabase via the project's **anon public** key (embedded in
`index.html`, RLS-protected — safe to ship). The `weather_scores` table has anon
`insert` and `select` policies; nothing sensitive is stored.
