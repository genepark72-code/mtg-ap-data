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
At 100 (capped/override): Donato (benchmark), Brom (raw 131), Tyler Jacobson (raw 112 — NRM plate CONFIRMED Jul 2026), Julie Bell (Lucas).
Excluded by design: social, obtainability, cost, card-count.

## Roster = 78 tier-one
This session added: 10 Koder/D&D-canon + Kaluta + Sienkiewicz + Julie Bell + comics batch 2 (Bryan Talbot Eisner-HoF-2024, Geof Darrow 3-Eisner, Dave Dorman, John Bolton, George Pratt). rk post = Koder-CONFIRMED (artist FB attestation of sale to Koder). Raoul Vitale D&D credit REMOVED (no D&D record). Dedup fixed (Randy rk Post merged).

## credentials.json — edits merged this session (Jul 2026, in the uploaded output)
- **Status cleanup:** Elliot Lang / Jeremy Wilson / Rebecca Guay `collection`→`commissioned` (committed, not in-hand — confirmed by Gene). Greg Spalenka placeholder→`gap` (not held). 18 tier-one reference artists (comics/D&D-canon batch) given `collection_status: gap`.
- **Meta note** corrected: roster.json is a 769-artist subset of 1,557 (was mis-stated as 138).
- **Post-clean status distribution:** 19 collection · 4 commissioned · 55 gap · 3 not_applicable. (19 in-hand tier-one reconciles to the 25-artist ledger: +6 non-tier-one pieces absent from credentials by design — Nils Hamm, Cacho Rubione, Vincent Proce, Jarel Threat, Drew Tucker, Domenico Cava.)
- **Enchanted verification field added:** new `nrm_enchanted_verified` on the 14 plate artists (see To-Do #1).

## OPEN TO-DO (next chat)
1. **Enchanted catalog photo pass — PARTIAL (Jul 2026).** 9 plates CATALOG-CONFIRMED in credentials.json (`nrm_enchanted_verified: catalog_2026-07`): Tyler Jacobson, Michael Whelan, Mark Zug, Eric Velhagen, Donato, Bob Eggleton, David Palumbo, Alessandra Pisano, Julie Bell. **STILL TO VERIFY in the Abbeville index** (currently held as plate, `verified: pending`): **McCaig** (88→73 if non-plate), **Allen Williams** (75→60), **Justin Sweet** (72→57), **Karla Ortiz** (72→57) — each a −15 swing. **Brom** moot (`pending_moot`, raw 131 pins him at 100 either way).
2. **Worlds & Realms index photo pass** — 9 artists pending D&D credit: Justin Sweet, Mark Zug (has A&A 6), Ryan Pancoast, Lindsey Look, Jesper Ejsing, Sam Burley, Andrew Mar, Daren Bader, Zoltan Boros. Also DiTerlizzi (A&A plate 12 — W&R would raise toward 24).
3. **A&A-qualified artists NOT yet added** (Gene to decide): Ralph Horsley, Jason Rainville, Michael Komarck, William O'Connor (d.2017), Fred Fields.
4. **Comics held:** Glenn Fabry (6th man), Jon J Muth (verify MTG cards on Scryfall — not in roster.json), Mike Dringenberg (fails gate).
5. **Billy Ireland verification** — email cartoons@osu.edu with the comics names (Kaluta, Sienkiewicz, Talbot, Darrow, Dorman, Bolton, Pratt) for authoritative holdings answer; 55-rung currently unpopulated.
6. **George Pratt fantasy-institutional** — gallery/IX record likely understates his 0.
7. Verify 6 "confirm-channel" AP URLs in open-now-contact-list.md.
8. **Tyler Jacobson — SCGCon LA (Oct 9–11 2026) — DECISION LOCKED (Jul 2026):**
   - **Commission = Drizzt/Guenhwyvar diptych, BOTH slots** (2 painted backs). Substrate: **2× Drizzt Do'Urden AFR #220 blanks** — both fronts = Jacobson's canonical $155k Drizzt art, so both sides his hand. Backs: **Drizzt** on one, **Guenhwyvar** on the other (mirrors the card's canonical summoner→token creation).
   - **Fire giant (2014 PHB) DROPPED.** 2024 MM cover = rejected alternative (all three 2024 core covers confirmed Jacobson; MM is his stated favorite — keep on file if the diptych ever changes).
   - **Routing:** hand the 2 blanks to Jacobson at con to lock deal + queue slot; **paint in-studio, NOT live**, so the pair coheres (matched palette, gazes talking across the pair).
   - **Framework:** AFR clears the gate — WotC in-house D&D IP, Standard-legal premier set, NOT third-party Universes Beyond.
   - **OPEN:** (a) **treatment** for the 2 blanks — regular #220 = clean canonical; borderless / extended-art (both still his art) = more unobstructed back space; **AVOID showcase** (different artist). (b) **source 2× AFR #220 blanks.** (c) confirm studio-vs-con routing with Jacobson.
   - **Concentration flag:** entire Jacobson commission now rests on one character pairing; the store Drizzt (below) adds a 3rd Drizzt object.
   - **Store buys (SEPARATE — not commission slots) — unchanged:** shop.tylerjacobsonart.com — Acererak $30 (DMG-lich back), Lathliss $10 (dragon back), Elminster $30, Drizzt $40 (Entreri/Guenhwyvar back), Lolth $20, Garruk Apex Predator $40. Tiamat NOT sold in store (but Tiamat IS a Jacobson AFR card — substrate available if ever wanted).
