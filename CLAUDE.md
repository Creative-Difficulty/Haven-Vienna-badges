# CLAUDE.md — Haven Vienna badges

This session's job is **finding suppliers for the parts**. Read footprints, values, hole sizes and pitches from the KiCad files (`badges/badges.kicad_pcb`, `badges/badges.kicad_sch`). Don't take them from this file.

## Constraints

- **55 badges**, plus a few spares. Ship to **Austria**.
- **Budget: ≤ €0.80 per badge for all parts excluding shipping**, plus **€45 total shipping** for all parts.
- The **55 CR2032 cells are already bought**, so they're not part of the €0.80. The battery holder still needs buying.
- **The PCB is already ordered.** Parts must fit the existing footprints, and footprints can't change.

## Decisions that aren't in the KiCad files

- **U1 must be a CMOS 555, not the LM555 in the schematic.** The supply is a single 3 V CR2032 (the net name `+6V` is misleading). A bipolar 555 needs ≥ 4.5 V and its output can't light the high-side LEDs. It must be DIP-8.
  - **Cheap pick:** XINLUDA **XD7555** (an ICM7555 clone, 2–18 V).
  - **Also fine:** TLC555CP, ICM7555IPA, LMC555CN.
- **LEDs:** **red or yellow** 5 mm. Blue and white (forward voltage about 3 V) barely light from 3 V.
- **Optional timing values:** R1 = 100k, R2 = 10k, C1 = 10 µF instead of 10k / 1k / 100 µF. Same blink rate, less wasted battery. Either set is acceptable; choose by price.
- **Avoid eBay/AliExpress "TLC555" or "7555" lots.** They're often relabelled bipolar NE555s that fail at 3 V.

## Research so far (LCSC, USD, snapshot 2026-10-18 — re-check)

The plan was a single LCSC order. EU VAT is charged at checkout, and shipping to Austria was roughly $10–25. The estimate was about $0.65 per badge.

| Part | LCSC | Seen | Note |
|---|---|---|---|
| XD7555, DIP-8 | C521188 | 50+ $0.1375 | only ~80 in stock |
| MYOUNG BS-07-A1BJ001, CR2032 holder | C2979167 | 50+ $0.304 | the footprint is made for this exact part; biggest cost item |
| 6×6 mm THT tactile switch | C2888886 | 50+ ~$0.013 | |
| 5 mm red LED | C87271 (one candidate) | "from $0.0192" at volume | small-quantity price not verified |
| Resistors, 1/4 W axial | — | — | not chosen yet |
| Electrolytic capacitor | — | — | not chosen yet; must match the footprint's lead spacing |

**Rejected as too expensive:** genuine TI TLC555CP from Reichelt.at (€1.00), Bürklin (€0.57 net + €8.30 shipping) and Mouser (~€0.73). LCSC C910886 was out of stock.
