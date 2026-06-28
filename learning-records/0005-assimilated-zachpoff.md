# Assimilated Zach Poff's DIY hydrophone/contact-mic knowledge

Harvested zachpoff.com (a high-trust practitioner already cited 3×). Added 9 new pages to [[RESOURCES.md]]
(Build & Components + Recorders). The durable value is a set of **corrections/sharpenings** that should guide
refinement of the build lessons — recorded here because they change what we'd teach, not just add links.

**Corrections to fold into lessons (not yet applied — pending review):**
1. **Resonance is a deliberate sensitivity↔fidelity TRADE, not just "bad."** A resonant piezo disc has *higher*
   output and a lower effective noise floor for weak signals; flat designs need more gain and hiss more on quiet
   sources. Reframe B1/B4 this way rather than "resonance = flaw." *(Poff: choosing-a-hydrophone, asf-1 review)*
3. **Resonant/budget elements roll off ~3–5 kHz — INSIDE the sperm-whale click band (~5–25 kHz).** So for our
   mission specifically, a resonant cheap disc *attenuates the very signal we want*: favour a FLAT element (PZT
   cylinder per B3, or a silicone-potted electret) + high sample rate. Strong mission-specific point for B1→B3 and
   T6. *(Poff: hti review, asf-1 review)*
4. **Damping flattens a disc:** felt kills mid-honk; bonding a hard metal disc to the back "dramatically flattens"
   response; edge-cutting shifts resonance up. Cheap quality win for B1/B3. *(Poff: building-contact-mics, 3d-printed)*
5. **Put the buffer IN the hydrophone**, not at the recorder (recorder-end is "more susceptible to interference").
   Reinforce B2/B3. *(Poff: choosing-a-hydrophone)*
6. **PIP buffer is a real alternative to Alex-Rice/phantom** for small 3.5 mm recorders (Poff's 2SK209 PIP preamp);
   and **phantom is wildly inefficient** for low-current front-ends → prefer PIP for long battery deployments. Add
   to B2 as a second path. *(Poff: pip-preamp, zoom-details)*
7. **Plasti-dip is shallow/short-term only** — slightly cuts treble, peels after days submerged; not for at-sea.
   B1 already frames it as a learning-build coating; make the "not for multi-day deployment" explicit. B3 is fine
   (urethane). *(Poff: building-contact-mics)*
8. **Gain-staging cuts both ways:** a high-sensitivity element (EM172) can *over-saturate* a recorder preamp — B4
   calibration/gain-staging should check clipping, not just under-gain. *(Poff: hydrophone-experiments-ii)*
9. **A non-piezo path exists:** silicone-potted electret (WM-61a/EM172) gives flat response with no "honk" — a
   viable alternative DIY element worth a sidebar in B1/B3. *(Poff: hydrophone-experiments, II)*
10. **Recorder pick:** Zoom **F3 (32-bit float, 192 kHz)** is ideal for clicks — worth naming in the Shopping List
    recorder table + T6. *(Poff: zoom-details)*

**Gaps confirmed (Poff does NOT cover; our mission still needs external sources):** cetacean click bandwidth/source
levels; deep-water pressure-rated potting & housings; PZT-cylinder element builds (core of B3); absolute calibration
in dB re 1 V/µPa; any multi-channel/array/TDOA/localization. These remain in [[RESOURCES.md]] #gaps.

Next: optionally apply corrections 1–10 as targeted lesson edits (mainly B1, B2, B3, B4, T6 + Shopping List), then
re-deploy. Awaiting Chris's go-ahead.
