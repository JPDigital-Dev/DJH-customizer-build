# KNOWN ISSUES — DJH Customizer (JPD-Q102)

## Logo assets (production blocker, not a demo blocker)
- Both supplied PNGs have an **opaque white background** — neither is transparent:
  - `assets/DJH Logo.png` — black lettering on white, full lockup, 500×500.
  - `assets/cropped-DJH-Logo-White.png` — white lettering on a **white** ground (unusable as-is), different crop (no "Attorneys, Notaries & Conveyancers" line).
- For the customizer demo, transparent derivatives were generated from `DJH Logo.png` (luminance-keyed):
  - `assets/DJH-logo-ink.png` / `assets/DJH-logo-paper.png` — full lockup (footer + source for crops)
  - `assets/DJH-monogram-ink.png` / `assets/DJH-monogram-paper.png` — compact DJH monogram (459×212); this is what travels into the nav (PDF p2 movement) and sits in the nav/mobile menu
  - `assets/DJH-subtitle-ink.png` / `assets/DJH-subtitle-paper.png` — "Attorneys, Notaries & Conveyancers" line (399×36); shown statically under the hero monogram so the hero still reads as the full lockup
- **Production needs a proper vector or high-res white full lockup (and monogram crop) from DJH/brand source.** The generated derivatives are raster keys from a 500×500 source — acceptable for the demo, not for final production at large hero sizes.

## Content held for client confirmation (do not resolve without DJH)
- **Boitumelo qualification line**: PDF says "LLB → LLM", but her bio places the LLM at UNISA (LLB at UFS). Literal "LLM, UFS" would be factually wrong. Shown as placeholder **"CONFIRM: LLM, UNISA?"** until confirmed.
- **Angelique join date**: printed "December 2025" verbatim per the PDF — needs a sanity confirmation with DJH.
- **Instagram / LinkedIn / Facebook URLs**: unconfirmed — social icons link to `#` with a visible "URLs to be confirmed" note.
- **All photography**: no photoshoot assets in the repo as of 2 Jul 2026 — every photo slot is a marked placeholder.
- **Reviews carousel**: scaffold in place; only the one confirmed review (Riney Groenewald) is shown and arrows/dots stay hidden until ≥2 real reviews are supplied.

## Production notes (demo intentionally stays single-file)
- **Attorney bios**: the demo opens bios in an in-page modal (keeps the single-file toggle system intact). For production, each attorney should get a **dedicated bio page with Person schema markup** (SEO / E-E-A-T for a trust-driven practice). Do not split the demo into pages.
