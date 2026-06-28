# 🐋 Hydrophone

An interactive, project-based course on **building hydrophones** and using them to **detect and
localize sperm whales** in the waters around Mauritius.

**▶ Live course:** https://chrisfraser.github.io/hydrophone/

Built lesson-by-lesson with [Claude Code](https://claude.com/claude-code) as a personal tutor.
Each lesson is a self-contained, interactive HTML page — calculators, spectrogram toys, and
quizzes included.

## Repo layout
| Path | What |
|---|---|
| `index.html` | Course home — the map of all lessons. |
| `lessons/` | Self-contained interactive lessons (`0001-*.html`, …). |
| `reference/` | Quick-reference docs: glossary, cheat sheets, algorithms. |
| `assets/` | Shared stylesheet + reusable widgets (quizzes, calculators). |
| `MISSION.md` | Why this course exists — the compass for every lesson. |
| `RESOURCES.md` | Curated, high-trust sources (knowledge) + communities (wisdom). |
| `learning-records/` | What's been learned — drives what comes next. |

## Publishing (GitHub Pages)
Served from the **root of `main`**. In repo Settings → Pages, set Source = `Deploy from a branch`,
Branch = `main` / `/ (root)`. A `.nojekyll` file is present so the HTML is served verbatim.

## Mission, in one line
Build a hydrophone → record confirmed sperm whale clicks → read their spectrograms → scale to an
array → **localize a whale by time-difference-of-arrival**, legally and ethically, off Mauritius.
