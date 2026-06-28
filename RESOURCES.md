# Hydrophones & Sperm Whale Localization — Resources

Curated, **verified** sources for the mission: build a hydrophone, detect sperm whale clicks off
Mauritius, and scale to a multi-element array for **localization**. Grouped Knowledge → Wisdom.
Every entry was opened and checked. Prune ruthlessly; annotate every link.

---

## Knowledge

### Fundamentals — underwater sound, sensitivity, the sonar equation
- [DOSITS — Hydrophone/Receiver](https://dosits.org/galleries/technology-gallery/basic-technology/hydrophonereceiver/) — Plain-language intro to what a hydrophone is (passive piezo pressure→voltage). *Start here before any math.*
- [DOSITS — Introduction to Decibels](https://dosits.org/science/advanced-topics/introduction-to-decibels/) — The decibel and the 1 µPa underwater reference (vs 20 µPa in air). *When dB references confuse you.*
- [DOSITS — Sound Speed](https://dosits.org/decision-makers/tutorials/science/sound-speed/) — Why ocean sound speed (~1450–1570 m/s) varies with temp/salinity/depth. *For ray bending & your local profile.*
- [DOSITS — Cylindrical vs Spherical Spreading](https://dosits.org/science/advanced-topics/cylindrical-vs-spherical-spreading/) — −6 dB/doubling (spherical) vs −3 dB (cylindrical, ducted). *When estimating how loud a whale is at your sensor.*
- [DOSITS — SONAR Equation](https://dosits.org/science/advanced-topics/sonar-equation/) — SL, TL, NL, DI, DT and signal excess. *Conceptual entry point.*
- [DOSITS — Passive Sonar Equation (worked)](https://dosits.org/science/advanced-topics/sonar-equation/sonar-equation-example-passive-sonar/) — SE = SL − TL − (NL − DI) − DT. *To compute whether you detect a clicking whale at range.*
- [DOSITS — Nyquist Sampling](https://dosits.org/science/advanced-topics/nyquist-sampling/) — Sample > 2× highest frequency; aliasing. *Justifies ≥96 kHz for clicks.*
- [DOSITS — Viewing & analyzing sound](https://dosits.org/science/measurement/how-are-sounds-viewed-and-analyzed/) — Waveforms vs spectrograms. *Before opening software.*
- [BOAT — Hydrophone Receiving Sensitivity](https://boat-fundamentals.readthedocs.io/en/latest/acoustics/RL_01_sensitivity.html) — The formula to turn recorded volts into SPL: `SPL = 20·log10(V/Vref) − M − G`. *For calibration & processing.*
- [NPL — Hydrophone Sensitivity (technical guide)](http://resource.npl.co.uk/acoustics/techguides/concepts/sen.html) — UK metrology institute's precise definition (dB re 1 V/µPa).
- [Dahl et al. — Underwater Ambient Noise (Acoustics Today)](https://acousticstoday.org/wp-content/uploads/2017/07/Article_3of4_from_ATCODK_3_1.pdf) — Readable review of ocean noise & the Wenz framework. *To set the noise floor (NL).*
- [Wenz Curves for Underwater Ambient Sound (JASA 2025)](https://pubs.aip.org/asa/jasa/article/157/5/R9/3346666/The-Wenz-curves-for-underwater-ambient-sound) — Canonical ambient-noise spectra 1 Hz–100 kHz. *Authoritative noise floor.*
- [Urick — *Principles of Underwater Sound* (Internet Archive)](https://archive.org/details/principlesofunde00uric) — The standard textbook (sonar eq, TL, noise, transducers). *Deep, citeable authority.*
- [WILDLABS — Introduction to Acoustic Monitoring (free course)](https://wildlabs.net/courses/introduction-acoustic-monitoring) — PAM fundamentals. *Before building or analysing.*

### Build & Components — make the instrument (~US$200–600)
- [The Gladys Hydrophone (Jules Ryckebusch) — Instructables](https://www.instructables.com/The-Gladys-Hydrophone/) — Step-by-step piezo + preamp + potting, ~$200. **Primary first-build recipe.**
- [Thomas Rex Beverly — DIY Hydrophone review](https://thomasrexbeverly.com/blogs/field-recording/diy-hydrophones) — Pro field recordist judged the ~$200 Gladys ≈ a $4,500 SoundTrap. *To decide whether DIY is good enough.*
- [Build Your Own Hydrophone (Stanford CCRMA 220a)](https://ccrma.stanford.edu/courses/220a/static/BuildYourOwnHydrophone.pdf) — University handout: element, waterproofing, preamp. *Structured alternative build.*
- [How to Build a DIY Hydrophone (Soundfly/Flypaper)](https://flypaper.soundfly.com/produce/how-to-build-a-diy-hydrophone/) — Cheapest possible piezo-disc prototype.
- [Choosing a Hydrophone for Field Recording (Zach Poff)](https://zachpoff.com/resources/choosing-a-hydrophone-for-field-recording/) — Impedance matching, sensitivity vs self-noise, resonant DIY vs flat commercial. *Before choosing element/preamp.*
- [Alex Rice Piezo Preamplifier (Zach Poff)](https://zachpoff.com/resources/alex-rice-piezo-preamplifier/) — Proven phantom-powered JFET preamp (~20 dB, 20 Hz–30 kHz). **The front-end electronics.**
- [Noise of a JFET Charge Amplifier for Piezo Sensors](https://www.researchgate.net/publication/320176627_Noise_of_a_JFET_Charge_Amplifier_for_Piezoelectric_Sensors) — Peer-reviewed noise analysis. *Charge vs voltage topology.*
- [Steminc — Piezo Cylinders/Tubes](https://www.steminc.com/PZT/en/piezo-cylinder) — Off-the-shelf PZT cylinders (25×22×12 mm ≈ $49). *Source the sensing element.*
- [APC International — Piezo Tubes](https://www.americanpiezo.com/products-services/piezo-tubes/) — Standard + custom PZT tubes. *For specific sizes/grades.*
- [NUWC XP-1 Acoustically Transparent Encapsulant (IEEE)](https://ieeexplore.ieee.org/document/1282434/) — What makes good potting (impedance ~1.71 MRayl ≈ seawater).
- [Polyurethane Elastomers for Transducer Encapsulation](https://www.researchgate.net/publication/347833250_Evaluation_of_Polyurethane_Elastomers_for_Encapsulation_of_Hydroacoustic_Transducers) — Selecting a potting compound for a serious build.
- [Aquarian Audio H2a](https://www.aquarianaudio.com/h2a-hydrophone.html) — ~$170–205 encapsulated hydrophone w/ integrated preamp. *Known-good reference or turnkey option.*
- [Autonomous Underwater Recorder on a Single-Board Computer (PLOS ONE)](https://pmc.ncbi.nlm.nih.gov/articles/PMC4468060/) — Full ~$500 Raspberry-Pi recorder + PZT cylinder + PVC housing to ~100 m (note 48 kHz ADC).
- [Teledyne RESON — Hydrophone FAQ](https://www.teledynemarine.com/en-us/products/SiteAssets/RESON/Hydrophone%20FAQ%20v1-1.pdf) — Commercial-grade specs: sensitivity, resonance, directivity, built-in preamps.
- [Cetacean Research C57 Hydrophone](https://www.cetaceanresearch.com/hydrophones/c57-hydrophone/index.html) — Research-grade cylinder (−187 dB, +20/+33 dB, 0.015–45 kHz, 370 m). *Design target/benchmark.*

**Zach Poff — DIY hydrophone & contact-mic resources** *(high-trust practitioner; the practical companion to the build lessons):*
- [Building A Simple Durable Contact Microphone (Zach Poff)](https://zachpoff.com/resources/building-contact-mics/) — Step-by-step piezo-disc assembly: soldering, foil shielding, felt/metal damping, plasti-dip. *Hands-on companion to B1; buy discs with wires pre-attached so you don't vaporise the plating.*
- [Choosing a Contact Mic For Field Recording (Zach Poff)](https://zachpoff.com/resources/choosing-a-contact-mic-for-field-recording/) — Clearest plain-language case for why a piezo needs a high-Z buffer, plus the resonance/"honk" spectrum. *For the T2/B2 impedance intuition.*
- [3D-Printed DIY Contact Microphone (Zach Poff)](https://zachpoff.com/resources/3d-printed-diy-contact-microphone/) — Bonding a 27 mm piezo to aluminium to flatten resonance + a printable strain-relief housing. *Rugged housing + damping ideas for B1/B3.*
- [Hydrophone Experiments II (Zach Poff)](https://zachpoff.com/resources/hydrophone-experiments-ii/) — Silicone-potted electret hydrophones (WM-61a vs Primo EM172 vs AQ-2000) + encapsulation do's/don'ts. *A flat, low-noise NON-piezo build path; soft silicone only — hard potting kills electret output.*
- [Hydrophone Review: HTI-92-WB / Ambient ASF-2 / DIY (Zach Poff)](https://zachpoff.com/resources/hydrophone-review-hti-92-wb-ambient-asf-2-diy-design/) — DIY-vs-commercial listening test (resonance, output, gain/noise). *Sets realistic expectations of a DIY build vs a pro reference.*
- [Hydrophone Review: Ambient ASF-1/ASF-2, Aquarian, JrF (Zach Poff)](https://zachpoff.com/resources/hydrophone-review-ambient-asf-1-asf-2-aquarian-audio-jrf/) — Flat-vs-resonant tradeoffs, HF limits, cost, durability. *When deciding whether you need accurate HF capture for clicks (budget units roll off ~3–5 kHz — inside the click band).*
- [PIP Stereo Piezo Preamplifier (Zach Poff)](https://zachpoff.com/resources/pip-stereo-piezo-preamplifier/) — 2SK209 JFET plug-in-power buffer with open PCB/3D files. *The alternative to the Alex Rice/phantom path when feeding a small 3.5 mm PIP recorder.*
- [Cheap Microphones for Ultrasound (Zach Poff)](https://zachpoff.com/resources/cheap-microphones-for-ultrasound/) — Cheap electret/MEMS capsules measured to ~100 kHz at 192 kHz (Primo EM258/EM172, Knowles SPU1410 MEMS). *When specifying HF capability + sample rate for click capture.*

### Sperm Whale Acoustics — the quarry
- [NOAA — Diving Deep into Sperm Whale Clicks](https://www.fisheries.noaa.gov/science-blog/diving-deep-sperm-whale-clicks) — Usual clicks, buzzes/creaks, codas/clans, the IPI size method. *Plain-language entry point.*
- [NOAA — Sperm Whale species page](https://www.fisheries.noaa.gov/species/sperm-whale) — Baseline biology: size, diving (~600 m/45 min), matrilineal units, status.
- [Sperm whale (Wikipedia)](https://en.wikipedia.org/wiki/Sperm_whale) — Well-cited click-type table (SL, freq, ICI). *Quick numeric cross-ref → chase the primaries.*
- [Goold & Jones 1995 — Click time/frequency characteristics](https://pubmed.ncbi.nlm.nih.gov/7560502/) — Classic spectra (peaks ~400 Hz & 2 kHz, energy to ≥12–15 kHz). *Sets spectrogram ranges.*
- [Møhl et al. 2003 — The monopulsed nature of sperm whale clicks](https://www.marinebioacoustics.com/files/2003/Mohl_et_al_2003a.pdf) — Landmark: directional, source levels up to ~236 dB re 1 µPa @1m. *Source-level physics.* ⚠ verify exact on-/off-axis numbers from the PDF.
- [Zimmer et al. 2005 — 3-D beam pattern of clicks](https://marinebioacoustics.wordpress.com/wp-content/uploads/2018/04/zimmer_et_al_2005c.pdf) — Highly directional forward beam. *Realistic SL/directionality for range estimates.*
- [Madsen et al. 2002 — Sound production (ultrasound tags)](https://journals.biologists.com/jeb/article/205/13/1899/8911/Sperm-whale-sound-production-studied-with) — Phonic-lips mechanism, multi-pulse structure, works at depth.
- [W. N. Atlantic acoustic abundance & dive behaviour (Sci Reports)](https://pmc.ncbi.nlm.nih.gov/articles/PMC9546825/) — Real PAM: HTI hydrophones, 192/500 kHz, click centroid 5–15 kHz, PAMGuard. *Sample-rate/array specs.*
- [Wideband fiber-optic array to sperm whales (Deep-Sea Research)](https://www.sciencedirect.com/science/article/abs/pii/S0967063706003268) — Flat 10 Hz–170 kHz, sampled 96 kHz. *Evidence ≥96 kHz is the working standard.*
- [Watwood et al. 2006 — Deep-diving foraging behaviour](https://pubmed.ncbi.nlm.nih.gov/16689963/) — Mean max depths 644–985 m; clicking starts early in descent. *When whales are acoustically active.*
- [Rendell & Whitehead 2003 — Vocal clans](https://research-portal.st-andrews.ac.uk/en/publications/vocal-clans-in-sperm-whales-emphyseter-macrocephalusem) — Coda dialects → clans across ocean basins.
- [Sharma et al. 2024 — Sperm whale 'phonetic alphabet'](https://www.nature.com/articles/s41467-024-47221-8) — Rhythm/tempo/rubato/ornamentation → 156+ codas. *Coda feature space.*
- [Frontiers 2025 — Survey of click-detection techniques](https://www.frontiersin.org/journals/marine-science/articles/10.3389/fmars.2025.1567001/full) — Energy/TKEO, wavelet, template, CNN (2002–2023). *Choosing a detection method.*
- [Detection via Teager-Kaiser Energy Operator](https://www.researchgate.net/publication/222823042_Detection_of_sperm_whale_clicks_based_on_the_Teager-Kaiser_energy_operator) — Foundational TKEO transient enhancer. *Lightweight time-domain detector.*

### Localization & Arrays — the summit
- [DOSITS — Hydrophone Arrays](https://dosits.org/galleries/technology-gallery/basic-technology/hydrophone-arrays/) — Why arrays give directionality/localization. *Single sensor → array.*
- [Skarsoulis et al. 2022 — Real-time sperm-whale localization observatory](https://www.frontiersin.org/journals/marine-science/articles/10.3389/fmars.2022.873888/full) — **3 moored hydrophones ~1–2 km apart, TDOA + surface reflections, 3-D out to ~7 km. The blueprint for your array.**
- [PAMGuard — Localization Overview](https://www.pamguard.org/olhelp/localisation/docs/localisation_overview.html) — Map of localizers (bearing, crossed bearings, hyperbolic/TDOA, TMA, 3-D).
- [PAMGuard — Types of Array](https://www.pamguard.org/olhelp/localisation/docs/localisation_arrays.html) — How many hydrophones each method needs (2 = ambiguous bearing … 5 = unambiguous 3-D). *Element count/geometry.*
- [PAMGuard — TDOA localization](https://www.pamguard.org/olhelp/localisation/docs/localisation_tdoa.html) — Cross-correlation TDOA; bearing (≥2) vs 3-D (≥4 distributed).
- [Tiemann et al. 2006 — 3-D localization from a single hydrophone](https://pubmed.ncbi.nlm.nih.gov/17069330/) — Range+depth via direct + multipath ray-tracing. *If you only have one/few sensors.*
- [Where's Whaledo (Snyder et al. 2024)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11142720/) · [code](https://github.com/MarineBioAcousticsRC/wheres-whaledo) — Open MATLAB pipeline: tetrahedral DOA + spaced TDOA. *Reproducible array workflow.*
- [Morrissey et al. — Sperm whale localization (Tongue of the Ocean)](https://glotin.univ-tln.fr/PIMC/DEMO/Morrissey_etal_NUWC_dataset1_2_results.pdf) — Worked FFT-threshold detection + TDOA + 2-D/3-D hyperbolic on a bottom array.
- [Growcott et al. 2011 — Body length from clicks](https://pubmed.ncbi.nlm.nih.gov/21786922/) — Validated **T = 1.258·IPI + 5.736** (IPI ms → length m).
- [Rhinelander & Dawson 2004 — IPI stability](https://www.researchgate.net/publication/8602554_Measuring_sperm_whales_from_their_clicks_Stability_of_interpulse_intervals_and_validation_that_they_indicate_whale_length) — IPI is stable & indicates length. *Justifies single-hydrophone sizing.*
- [Barlow et al. 2016 — Free-floating vertical arrays (DASBR)](https://pubs.aip.org/asa/jasa/article/140/5/EL399/679287/Cetacean-acoustic-detections-from-free-floating) — Drifting 2-element array (192 kHz, ~100 m) detecting sperm whales. *Low-cost drifting/sonobuoy design.*
- [A generalized beamformer for marine-mammal localization (Applied Acoustics 2006)](https://www.sciencedirect.com/science/article/abs/pii/S0003682X06001125) — Beyond pairwise correlation to steered-response/beamforming.

### Software & Signal Processing
- [PAMGuard — official site](https://www.pamguard.org/) — World-leading free open-source detect/classify/localize software for clicks. **Main no-code PAM tool.**
- [PAMGuard — GitHub (GPL-3.0, Java)](https://github.com/PAMGuard/PAMGuard) — Beamforming, large-aperture localizer, TMA; actively maintained (v2.02.18, Feb 2026).
- [PAMGuard — Click Classification help](https://www.pamguard.org/olhelp/detectors/clickDetectorHelp/docs/ClickDetector_clickClassification.html) — Basic vs Frequency-Sweep classifiers.
- [PAMGuard — Click Train Detector help](https://github.com/PAMGuard/PAMGuard/blob/main/src/clickTrainDetector/click_train_help.md) — Groups clicks into per-animal trains.
- [Raven Lite (Cornell)](https://www.ravensoundsoftware.com/software/raven-lite/) — Free recording/spectrogram viewing. *Easy free starting point.*
- [Raven Pro (Cornell)](https://www.ravensoundsoftware.com/software/raven-pro/) — Research-grade measurement, spectrogram correlation, Learning Detector ML.
- [Raven training videos (Cornell)](https://www.birds.cornell.edu/ccb/training-materials-sound-analysis-software/) — Free hands-on tutorials.
- [Cornell — Virtual Lab: Sound Analysis Principles](https://www.birds.cornell.edu/ccb/virtual-lab-sound-analysis-principles/) — Free self-paced digital-audio & spectrogram fundamentals.
- [Audacity — Spectrogram View (manual)](https://manual.audacityteam.org/man/spectrogram_view.html) — Clicks = vertical lines; configurable window/freq/gain.
- [GCC-PHAT — MATLAB `gccphat`](https://www.mathworks.com/help/phased/ref/gccphat.html) — Phase-whitened TDOA. *Robust delay estimation.*
- [GCC-PHAT tutorial (Anguera thesis)](https://xavieranguera.com/phdthesis/node92.html) — Concise GCC/PHAT derivation. *Math before coding.*
- [python-soundfile](https://python-soundfile.readthedocs.io/) — WAV/FLAC ↔ NumPy, block-wise reads of big files. *Reliable I/O without resampling.*
- [scipy.signal — spectrogram / ShortTimeFFT](https://docs.scipy.org/doc/scipy/reference/generated/scipy.signal.spectrogram.html) — Programmatic spectrograms (new code → ShortTimeFFT).
- [librosa](https://librosa.org/doc/main/) — STFT/spectrograms/onsets (use `sr=None, mono=False` for ultrasonic clicks).
- [scikit-maad](https://besjournals.onlinelibrary.wiley.com/doi/10.1111/2041-210X.13711) — Audio loading/segmentation, acoustic features, SPL.
- [PyPAM](https://github.com/lifewatch/pypam) — Chunked underwater-audio processing w/ hydrophone metadata. *Python ingestion pipeline.*
- [Ketos](https://docs.meridian.cs.dal.ca/ketos/) · [OpenSoundscape](http://opensoundscape.org/en/latest/) · [ANIMAL-SPOT](https://github.com/ChristianBergler/ANIMAL-SPOT) — ML detector toolkits *(out of scope until manual detection works — see MISSION).*
- [Watkins Marine Mammal Sound Database (WHOI)](https://www.watkins-marinemammalsounddatabase.org/) — ~2,000 curated, freely downloadable marine-mammal recordings including sperm whales. *Free practice data for the theory phase — open these in Audacity/Raven to read real clicks before you own a hydrophone.*

### Recorders (array-capable, ≥96 kHz)
- [HydroMoth / AudioMoth (Open Acoustic Devices)](https://www.openacousticdevices.info/audiomoth) — Low-cost recorder up to 384 kHz, underwater case, 3×AA. *Cheap autonomous node.*
- [Zoom F6](https://zoomcorp.com/en/us/field-recorders/field-recorders/f6/) — 6 XLR, up to 192 kHz, 32-bit float, +24/+48 V phantom. **Value choice for a phantom-powered array.**
- [Sound Devices MixPre-6 II](https://www.sounddevices.com/mixpre-6-ii-specifications/) — Up to 192 kHz/32-bit float, 10 Hz–80 kHz, ultra-low-noise preamps. *Premium option.*
- [Orcasound — Pi node (hydrophone→headphone)](https://www.orcasound.net/2018/04/27/orcasounds-new-live-audio-solution-from-hydrophone-to-headphone-with-a-raspberry-pi-computer-and-hls-dash-streaming-software/) — Live-streaming Pi + Pisound (192 kHz, ~$800, open source). *Cabled real-time node.*
- [Zoom Recorder Technical Details (Zach Poff)](https://zachpoff.com/resources/zoom-recorder-technical-details/) — Plug-in-power vs phantom behaviour and quirks of H1n/H5/H2n/F3. *When picking a deck and powering a JFET buffer; the **Zoom F3 (32-bit float, 192 kHz)** is ideal for ultrasonic clicks, and note phantom is wildly inefficient for low-current front-ends (favour PIP for long battery deployments).*

### Mauritius & Regulations
- [Sarano et al. — Social units & vocal clans in Mauritius (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8074673/) — Resident ~28-whale matrilineal "Irène's group", year-round. *Who/where/when for deployment.*
- [Mauritius IPI–body-length/age study (Nature Sci Reports 2024)](https://www.nature.com/articles/s41598-024-51194-5) — Local population's exact click structure & sizes.
- [Indian-Ocean male sperm whales: kinship & fidelity (Frontiers 2022)](https://www.frontiersin.org/journals/marine-science/articles/10.3389/fmars.2022.815684/full) — 26 males off W. Mauritius 2011–2020, ~8-day residency, with coordinates.
- [Mascarene Islands IMMA factsheet (IUCN MMPATF)](https://www.marinemammalhabitat.org/factsheets/mascarene-islands-associated-oceanic-features/) — W. Mauritius slope = key breeding/feeding habitat; year-round residents.
- [MMCO / Maubydick — Cetaceans](https://www.mmco.mu/cetaceane/) — Local NGO monitoring since 2011; resident pop. <40 (38 catalogued).
- [Longitude 181 — La Voix des Cachalots](https://www.longitude181.org/programme-cetaces-cachalots/) — Sarano's annual Mauritius study since 2015 (Irène clan).
- [Charles Telfair Centre — Mascarene IMMA background](https://charlestelfaircentre.com/the-mascarene-islands-identified-as-an-important-marine-mammal-area/) — Long-term study context (<40 individuals).
- [**Dolphin & Whale Watching Regulations 2012 (GN 154)**](https://faolex.fao.org/docs/pdf/mat116851.pdf) — **Statutory text: 100 m prohibited / 100–200 m regulated zones, no-wake parallel approach.** *Authoritative legal source.*
- [Tourism Authority — Dolphin & Whale Watching communiqué](https://www.tourismauthority.mu/communique-dolphin-and-whale-watching/) — Swimming/diving/snorkelling with whales is an offence. *Current enforced position.*
- [EPCO — Swimming with large cetaceans](https://epco.ngo/swimming-with-large-cetaceans/) — Plain-language: 3 Mar 2020 swim/dive ban + 100 m boat rule.
- [Albion Fisheries Research Centre (AFRC)](https://blueconomy.govmu.org/Pages/Departments/Albion%20Fisheries%20Research%20Centre%20(AFRC)/AFRC.aspx) — Govt research centre running the marine parks. *Permitting/data context.*
- [NOAA/BOEM — Minimum PAM Recommendations (Van Parijs et al. 2021)](https://www.frontiersin.org/journals/marine-science/articles/10.3389/fmars.2021.760840/full) — Sensitivity/bandwidth/calibration standards, sample rate by species, hydrophone count for localization. *Spec a defensible system.*

---

## Wisdom (Communities)

- [WILDLABS Acoustics group](https://wildlabs.net/groups/acoustics) — Large active conservation-tech PAM community. **First stop for build/hardware feedback.**
- [MMCO / Maubydick (Mauritius)](https://www.mmco.mu/) — Local lead on the resident sperm whales since 2011. **Closest match to the exact mission/location — likely collaborator.**
- [Longitude 181 — La Voix des Cachalots](https://www.longitude181.org/programme-cetaces-cachalots/) — Sarano's Mauritius programme. *Local fieldwork context / partnership.*
- [PAMGuard `pamguard-user` mailing list](https://sourceforge.net/p/pamguard/mailman/pamguard-user/) — For detection/classification/localization questions (email the list or support@pamguard.org; web forum dead since 2019).
- [Orcasound community](https://www.orcasound.net/) — Open-source cooperative hydrophone network (Zulip + weekly meetings). *Building/operating a streaming Pi node.*
- [Open Acoustic Devices forum (AudioMoth/HydroMoth)](https://www.openacousticdevices.info/support) — Bare-hydrophone connection, preamps, underwater enclosures.
- [MicBuilders (groups.io)](https://groups.io/g/MicBuilders/topic/diy_hydrophone/71488789) — DIY mic/hydrophone preamp & potting questions.
- [Adafruit Discord](https://www.adafruit.com/discord) — Large maker community for the electronics side of a first build.
- [r/fieldrecording](https://www.reddit.com/r/fieldrecording/) — Quick informal sanity-checks on builds, preamps, recorders.
- [MARMAM listserv](https://lists.uvic.ca/mailman/listinfo/marmam) — Standard marine-mammal research listserv (6,000+). *Papers, researchers — once past the hobby stage.*
- [Dominica Sperm Whale Project (DSWP)](https://www.thespermwhaleproject.org/about) — Shane Gero's study; canonical coda/clan methods & bibliography.
- [Project CETI](https://www.projectceti.org/) — State-of-the-art sperm-whale array + ML off Dominica. *Follow for cutting-edge methods (not a hobbyist data channel).*
- [K. Lisa Yang Center for Conservation Bioacoustics (Cornell)](https://www.birds.cornell.edu/ccb/) — Raven software, free training, marine PAM methods.
- [ASA Technical Committee on Animal Bioacoustics](https://tcabasa.org/) — Professional acoustics expertise & conference sessions.

---

## Gaps (drive future research)

These matter for the mission but lack a single strong source — flagged so future sessions can hunt:

1. **Beginner potting/waterproofing** tutorial for a first cheap build (existing guides jump to preamps/encapsulants).
2. **Mauritius-specific sound-speed profile / bathymetry / CTD** for the western slope — needed to model local ray bending & detection range.
3. **Vetted multi-hydrophone array BOM** with current prices/suppliers inside the $200–600 budget. *Partly
   addressed:* `reference/shopping-list.html` now gives concrete per-project BOMs for the single-unit builds
   (Projects A–C) and an **outline** for the array (Project D); array specifics + **live-verified prices /
   Mauritius-shippable suppliers** still pending.
4. **Time-synchronizing multiple independent recorders** (GPS/PPS, clock-drift correction) — essential for TDOA, absent from single-node refs.
5. **Mauritius scientific research / deployment permit process** (AFRC / Tourism Authority) — only the *watching* rules are documented.
6. **Beginner end-to-end PAMGuard walkthrough for sperm-whale clicks** (detector → click-train → localization).
7. **Safe small-boat deployment / mooring / recovery** of hydrophones over a deep continental slope.
8. ⚠ **Re-verify exact source-level / beam-pattern numbers** from Møhl 2003 & Zimmer 2005 (PDFs didn't text-parse) before hard-coding them into calculators.
