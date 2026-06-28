# Working Notes & Preferences

## How Chris wants to be taught
- Treat as **medium-to-novice**: has touched electronics, programming/DSP, marine/boating, and
  physics, but it's **rusty**. Re-establish fundamentals; use real terminology but don't assume retention.
- **Balanced math**: formulas + worked examples + **interactive calculators**. Intuition first, math to back it.
- Wants **interactive graphics/tools** in lessons wherever possible (calculators, simulators,
  spectrogram toys, quizzes).
- In chat, be **extremely concise** (global pref). Sacrifice grammar for concision. (Lessons themselves
  are full and beautiful — concision applies to our conversation, not the teaching artifacts.)

## Delivery
- Lessons published via **GitHub Pages**: repo `github.com/chrisfraser/hydrophone`.
- Serve from **repo root** — `index.html` is the course home; `.nojekyll` present so plain HTML is served as-is.
- Each lesson is a standalone HTML file in `lessons/`, linked from `index.html`, cross-linked to `reference/`.
- All lessons link the shared stylesheet `assets/styles.css` and shared widgets in `assets/`.

## Sequencing preference (set 2026-06-28) — THEORY FIRST
Chris asked to **front-load all theory before the hardware builds**, because hardware is slow to order/receive
(esp. shipped to Mauritius). So:
- Course is reorganized into **Phases**: 1 Theory → 2 Procurement → 3 Build → 4 Array (see `index.html`).
- A **Shopping List reference** (`reference/shopping-list.html`, sibling to the Glossary) lets him buy hardware
  **up front** while doing theory. Organized per project (A starter / B preamp / C serious / D array), approx
  prices, supplier links, lead-time flags, 3-tier purchase plan. Prices are APPROX — offered a live price-check later.
- The existing build lesson ("Your First Underwater Ear") is now **B1 in Phase 3**, not "lesson 2 in sequence".
- Next teaching priority is **Phase 1 theory lessons** (T2 Pressure→Voltage next), NOT more build lessons.

## Mission arc (summit = full localization/tracking)
Conceptual through-line: single hydrophone → detect/record clicks → read spectrograms → 2-element bearing →
multi-element array + TDOA localization. Front-load a buildable, motivating win.

## Build constraints to keep visible
- Budget ~US$200–600 → research-ish element + low-noise preamp + **array-capable multi-channel recorder**.
- Sperm whale clicks are **broadband and very loud** → recorder must **sample high (≥96 kHz target)**.
  Keep this constraint front-of-mind in every build lesson.

## TODO / open threads
- Confirm whether Chris has a boat / regular sea access (affects deployment lessons).
- Decide GitHub Pages branch in repo settings (root of `main`). Offer to commit + push when scaffold is ready.
