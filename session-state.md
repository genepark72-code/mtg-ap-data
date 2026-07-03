# MTG Painted-AP Collection — Session State / Handoff
*Gene Park (@genepark72-code). Drop this + `credentials.json` (as .txt) into a new chat to resume instantly.*

## What this is
A credential-gated tier-one MTG-artist roster + multi-axis **Artist Prestige Score** model, for a legacy painted artist-proof (AP) collection (30-yr hold). Source of truth = `credentials.json` in repo `genepark72-code/mtg-ap-data`. **73 tier-one artists.**

## CRITICAL operating rules (learned the hard way)
- **Claude CANNOT read the GitHub repo** — blob fetches serve a stale cache, raw is robots-blocked. Gene is the source of truth for what's live. To work on a file, **upload it into the chat** (rename `.json` → `.txt` if it uploads empty).
- **Card counts / roster membership:** check `roster.json` FIRST; if an artist is absent, confirm on **Scryfall directly** (casualplaneswalker/roster.json is a partial scrape ~758 of 1557, and misses older/crossover/Secret Lair artists). Do NOT trust old forum counts.
- **Full-vector sweep when adding/editing any artist:** check every axis (awards+years, NRM Enchanted, D&D books, Lucas/Eisner, institutional incl. IX Main Show/CIC, MTG count, obtainable/deceased) — not just the one that triggered inclusion.

## Prestige model (FINAL this session — calibrated, three-domain)
**prestige = raw ÷ 100 (Donato Giancola's raw = 100 = the benchmark), capped at 100. Lucas Museum acquisition = OVERRIDE to 100.**
raw = Credentials(≤30) + Institutional + Documentary(≤10) + Legacy(≤5)

**Institutional = THREE stacked domain rungs (each = single highest rung reached):**
- **FANTASY (≤55):** gallery 15 / juried IX-MainShow+CIC 22 / gallery+ 28 / museum 35 / NRM-Enchanted non-plate 40 / **NRM-Enchanted PLATE 55**
- **D&D (≤40):** book-proxy A&A + Worlds&Realms additive (mention 6 / plate 12, cap 34) / **Koder-Eidolon confirmed 40** (Koder collection = Eidolon museum, counted once)
- **COMICS (≤55):** juried exhibition 22 / Eisner win 12 ea + Harvey 6 ea (cap 34) / **Eisner Hall of Fame 40** / **Billy Ireland Museum collection 55**
Credentials: base 12 + apex (Hugo/WFA/Grandmaster/Chesley-Lifetime +6 ea, cap 12) + depth (+6 if ≥4 award-years, +3 if ≥2).
At 100 (capped/override): Donato (benchmark), Brom (raw 131), Tyler Jacobson (raw 112 — NRM plate UNVERIFIED), Julie Bell (Lucas).
Excluded by design: social, obtainability, cost, card-count.

## Roster = 78 tier-one
This session added: 10 Koder/D&D-canon + Kaluta + Sienkiewicz + Julie Bell + comics batch 2 (Bryan Talbot Eisner-HoF-2024, Geof Darrow 3-Eisner, Dave Dorman, John Bolton, George Pratt). rk post = Koder-CONFIRMED (artist FB attestation of sale to Koder). Raoul Vitale D&D credit REMOVED (no D&D record). Dedup fixed (Randy rk Post merged).

## OPEN TO-DO (next chat)
1. **Enchanted catalog photo pass** — verify plate vs non-plate for ALL nrm_enchanted artists (Tyler Jacobson's 100 hinges on it).
2. **Worlds & Realms index photo pass** — 9 artists pending D&D credit: Justin Sweet, Mark Zug (has A&A 6), Ryan Pancoast, Lindsey Look, Jesper Ejsing, Sam Burley, Andrew Mar, Daren Bader, Zoltan Boros. Also DiTerlizzi (A&A plate 12 — W&R would raise toward 24).
3. **A&A-qualified artists NOT yet added** (Gene to decide): Ralph Horsley, Jason Rainville, Michael Komarck, William O'Connor (d.2017), Fred Fields.
4. **Comics held:** Glenn Fabry (6th man), Jon J Muth (verify MTG cards on Scryfall — not in roster.json), Mike Dringenberg (fails gate).
5. **Billy Ireland verification** — email cartoons@osu.edu with the comics names (Kaluta, Sienkiewicz, Talbot, Darrow, Dorman, Bolton, Pratt) for authoritative holdings answer; 55-rung currently unpopulated.
6. **George Pratt fantasy-institutional** — gallery/IX record likely understates his 0.
7. Verify 6 "confirm-channel" AP URLs in open-now-contact-list.md.
8. **Tyler Jacobson commission (planned this session):** buy now from shop.tylerjacobsonart.com — Acererak $30 (DMG-lich back), Lathliss $10 (dragon back), Elminster $30, Drizzt $40 (Entreri/Guenhwyvar back), Lolth $20, Garruk Apex Predator $40. SCGCon LA asks: PHB fire-giant substrate (his pick), 2024 MM cover piece. Tiamat NOT sold in store.
