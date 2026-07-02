# Tier-One Credential Audit — Methodology (the permanent fix)

**Problem this solves:** tier-one artists kept getting missed or misfiled. Root cause was a *reactive, artist-first* process (evaluate a name only when it comes up) plus a bias toward the famous credentials (Chesley/Hugo/Spectrum Gold), which left the quiet-but-qualifying credentials (SOI/SILA Gold+Silver, Spectrum non-headline categories, Comm Arts) as a permanent blind spot.

**The fix:** build the roster by INTERSECTION, credential-first, with cited verification. This is exhaustive by construction — an artist cannot be "missed" because we iterate the award lists, not the artists.

---

## The intersection

Complete tier-one set = **(artists who won a gate credential) ∩ (MTG illustrators)**

- **Award side (enumerable sources):**
  - Chesley Awards — sfadb.com / sf-encyclopedia.com (complete winner lists, all categories, all years)
  - Spectrum Gold **and Silver** — sfadb.com (all categories: Book, Editorial, Advertising, Institutional, Comics, Unpublished, Dimensional, Gaming)
  - Hugo Best Professional Artist — complete winner list
  - World Fantasy Award — Artist — complete winner list
  - British Fantasy Award — Artist; Locus Award — Artist — complete winner lists
  - Society of Illustrators (NY) annual Gold/Silver medalists
  - Society of Illustrators LA (SI-LA / "Illustration West") Gold/Silver medalists
  - Communication Arts Illustration Annual — juried selections
  - National Portrait Gallery London (BP Portrait Award) — selected exhibitions
- **MTG side:** Wikipedia "List of Magic: The Gathering artists" (~600) or repo `roster.json`.

**Method:** for each award list, walk the winners and flag any who also appear on the MTG artist list. Every flagged name belongs in `credentials.json`. Anyone flagged but absent = a real gap you can now *see* instead of stumble into.

---

## Canonical per-artist checklist (run on EVERY artist, in this fixed order)

Do not stop at the first "no." Check all ten:

1. Hugo — Best Professional Artist (win)
2. World Fantasy — Artist (win)
3. Chesley — any category (win)
4. British Fantasy — Artist (win)
5. Locus — Artist (win)
6. Spectrum — Gold, **any category** (win)
7. Spectrum — Silver, any category (if you count Silver — confirm your rule)
8. SOI (NY) — Gold or Silver medal
9. SI-LA — Gold or Silver medal
10. Communication Arts Annual / NPG London — selection

Plus standalone credentials tracked separately: **Norman Rockwell "Enchanted" exhibition**; museum-exhibition / gallery-CV exception; OG-lane exception.

---

## Data discipline (stops silent drift)

Add to each artist in `credentials.json`:

- `verified`: source + date, e.g. `"sfadb 2026-07"`. No source = treated as UNVERIFIED, not assumed true.
- Keep `null` meaning *unverified*, never zero.
- When a credential is asserted from memory or a secondary source, mark it `"unverified"` until checked against a primary list (sfadb / the awarding body).

This is what would have caught both failure modes: the missing SOI/SILA Golds (nothing verified them in) and the wrongly-doubted Palumbo Gold (recall overrode the record).

---

## Annual refresh (keeps it complete going forward)

New tier-one artists can ONLY appear via a new award. So once a year, when each body announces winners, check that year's:

- Chesley winners, Spectrum Gold/Silver, Hugo/WFA/Locus/British Fantasy artist winners, SOI-NY + SI-LA medalists

…against the MTG artist list. New MTG-artist winners get added; that's the entire maintenance cost. One small pass per year keeps the roster exhaustive.

---

## Status

- [x] **Chesley** winners intersected with MTG artists (7/2026) → found: Rob Alexander, Michael C. Hayes, Wylie Beckert, Mark Zug, Brom, Jaime Jones, Stephan Martiniere, Michael Whelan.
- [x] **Spectrum Gold** winners intersected (7/2026) → found: Jesper Ejsing, Kekai Kotaki, Karla Ortiz, Cynthia Sheppard, Iain McCaig — **and corrected two in-hand artists misfiled as exceptions: Daren Bader, Andrew Mar** (both Spectrum Gold).
- [x] `obtainable` flag added (yes/verify/limited/drops-only/no). Michael Whelan flagged `no` — tier-one by credential, no AP/commission pathway.
- [x] Blind-spot credentials (SOI/SILA, Spectrum non-headline) confirmed as the recurring failure locus.
- [x] **Remaining award lists intersected (7/2026):** Hugo, World Fantasy, Locus, British Fantasy → no new MTG names (all their MTG winners already captured: Whelan, Eggleton, Donato, Cai, Dillon, Martiniere). **SOI-NY + SI-LA medalists** straggler-checked → no new MTG medalists beyond those already in roster (Benbassat, Guay, Wilson, Lang, Spalenka). **SWEEP COMPLETE across all gate credentials.**
- [ ] **Held out — MTG status unconfirmed, NOT asserted** (verify via direct Scryfall artist lookup before adding): James Jean, Kinuko Craft, Sam Weber, Vance Kovacs, Charles Vess, Allen Williams, Sam Burley, Vanessa Lemen.
- [ ] Add per-credential `verified` source+date across `credentials.json`.
- [x] **Annual refresh is now the only upkeep** — each award season, intersect that year's new winners against the MTG artist list.
