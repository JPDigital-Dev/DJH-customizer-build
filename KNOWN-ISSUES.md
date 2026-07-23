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
- ~~**Boitumelo qualification line**~~ — **RESOLVED 21 Jul 2026:** DJH confirmed **LLM, UFS**. The earlier "CONFIRM: LLM, UNISA?" placeholder was a wrong guess; see assets/CLAUDE.md §7/§4.
- **Angelique join date**: printed "December 2025" verbatim per the PDF — still needs a sanity confirmation with DJH.
- ~~**Instagram / LinkedIn / Facebook URLs**~~ — **RESOLVED 21 Jul 2026:** all three confirmed and live; see assets/CLAUDE.md §4.
- ~~**All photography**~~ — **RESOLVED 21 Jul 2026:** WeTransfer photo drop landed and every remaining slot is filled. Hero, all four attorney cards, all eight support-staff cards, the Reviews-section background, the About-section story image (`about-story.jpg`), and the Contact-section second photo (`contact-team.jpg`) all use real photos now (map in assets/CLAUDE.md §7; the last two were placed per WEBSITE_LAYOUT.pdf pages 3 and 8). No placeholder images remain.
- ~~**Two photo identities assigned by elimination**~~ / ~~**`mignon-de-jager-hattingh.jpg` confirmed wrong**~~ — **RESOLVED 21 Jul 2026 (photo re-drop):** Jan re-supplied the full raw photo set (same shoot, original camera filenames). WEBSITE_LAYOUT.pdf pages 5–6 turned out to show the client's own labelled reference photos for all 4 attorneys and all 8 support staff, so every identity this pass was confirmed by direct face-match against those labelled images — not elimination. This corrected two mismatches from the prior pass: `mignon-de-jager-hattingh.jpg` is now `_MG_7468` (previously wrongly `_MG_7524`, which is actually Sifiso), and `sifiso-mokwana.jpg` is now `_MG_7524` (previously wrongly assigned to `_MG_7369`, which is actually Angelique). `mandla-mahlangu.jpg` (`_MG_7532`) was independently re-confirmed correct. Full current source→destination map in `assets/CLAUDE.md` §12. Mignon's Professionals card now shows her real photo instead of the initials placeholder.
- **Reviews carousel**: scaffold in place; only the one confirmed review (Riney Groenewald) is shown and arrows/dots stay hidden until ≥2 real reviews are supplied.

## Production notes (demo intentionally stays single-file)
- **Attorney bios**: the demo opens bios in an in-page modal (keeps the file single-page). For production, each attorney should get a **dedicated bio page with Person schema markup** (SEO / E-E-A-T for a trust-driven practice). Do not split the demo into pages.
- **21 Jul 2026 — the three-axis customizer (hero style / accent palette / display font) has been retired**: DJH picked Light hero / Peru / Cormorant, so the `cz-panel` toggle UI and its JS/CSS were removed from `index.html`. See assets/CLAUDE.md §1/§7.
