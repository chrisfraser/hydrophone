# Mission: Hydrophones for Sperm Whale Localization (Mauritius)

## Why
Chris wants to build his own hydrophone(s) from accessible components and use them to
acoustically **find and ultimately track ("localize") the resident sperm whales** in the
waters around Mauritius — turning a personal fascination into the real-world ability to
detect, follow, and study these animals himself in the open ocean.

## Success looks like
- Builds a working, low-noise hydrophone (~US$200–600) and records **confirmed sperm whale
  clicks/codas** off Mauritius.
- Reads a **spectrogram** of whale clicks and identifies inter-click interval, creaks, and codas.
- Scales to a **multi-element array** and uses **time-difference-of-arrival (TDOA)** to estimate
  a bearing, then a position, of a clicking whale.
- Operates **legally and ethically** within Mauritius marine-mammal regulations.

## Constraints
- Treat learner as **medium-to-novice**: real foundations in electronics, DSP, marine/boating,
  and physics, but rusty — re-establish fundamentals, don't assume retention.
- Budget for first build: **serious, ~US$200–600**.
- **Balanced math**: key formulas (decibels, sonar equation, TDOA) with worked examples +
  interactive calculators.
- Lessons must be self-contained, beautiful, **interactive** HTML, publishable via **GitHub Pages**
  (github.com/chrisfraser/hydrophone).

## Mission arc (summit = full localization/tracking)
**Theory-first, then hardware** (chosen because parts are slow to reach Mauritius — learn while they ship):
- **Phase 1 — Theory:** sound & the click → pressure→voltage → decibels → spectrograms → clicks/codas →
  Nyquist → sonar equation → detection → IPI sizing → TDOA → arrays/hyperbolic localization → tracking & law.
  (No hardware; uses free software + public recordings.)
- **Phase 2 — Procurement:** order long-lead hardware up front via the Shopping List reference
  (`reference/shopping-list.html`), organized per project, mapped to the ~$200–600 budget.
- **Phase 3 — Build:** cheap piezo ear → preamp → serious PZT-cylinder build → calibration.
- **Phase 4 — Array:** multi-element array + TDOA localization in the water (the summit).

Conceptual through-line is unchanged: single hydrophone → record clicks → spectrograms → bearing → array/TDOA.

## Out of scope (for now)
- **Active sonar / pinging** — we listen passively (ethical + legal).
- **Machine-learning click classifiers** — until basic detection + localization work by hand.
- Deep electronics/DSP theory beyond what the build and the localization math actually need.
