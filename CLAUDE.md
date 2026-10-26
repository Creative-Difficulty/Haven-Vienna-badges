# CLAUDE.md — Haven Vienna badges

The supplier search is done; the order list is in `SUPPLIERS.md` (LCSC, within budget). `ALTERNATIVE-SUPPLIERS.md` is an EU-only fallback (Pollin and Reichelt), which comes to about €195. Read footprints, values, hole sizes and pitches from the KiCad files (`badges/badges.kicad_pcb`, `badges/badges.kicad_sch`). Don't take them from this file.

## Constraints

- **75 badges**, plus a few spares. Ship to **Austria**. The event is on **14 Nov 2026**.
- **Budget: €100 total for all parts, including shipping and VAT.**
- The CR2032 cells are handled separately and aren't part of the budget. The battery holder is.
- **The PCB is already ordered** (at least 75 boards). Parts must fit the existing footprints, and footprints can't change.
- SW1 is a momentary button on purpose: the badge blinks only while it's held.

## Decisions that aren't in the KiCad files

- **U1 must be a CMOS 555, not the LM555 in the schematic.** The supply is a single 3 V CR2032 (the net name `+6V` is misleading). A bipolar 555 needs ≥ 4.5 V and its output can't light the high-side LEDs. It must be DIP-8.
  - **Chosen:** XINLUDA **XD551** (a TLC555 clone, 2–15 V). Its output can source about 2.5× more current than 7555-type parts, which D4–D6 need.
  - ICM7555-type parts (XD7555) work, but at 3 V they source too little current and D4–D6 end up dim.
- **LED colours (decided 2026-10-27):** D1 lime green, D2 orange, D3 white, D4 red, D5 orange, D6 red, all from the Guiguang 5 mm 45° family.
  - White and green must stay in D1–D3. Those hang from + and the 555 pulls them low, which it does strongly. D4–D6 are driven by the output going high, which is weak at 3 V and only works for low-voltage LEDs.
  - The green is lime (570 nm), because emerald (525 nm) needs about 2.5 V, like white.
  - White's brightness varies between badges and with cell voltage. With a 3 V cell and this PCB, nothing fixes that.
- **Resistors balance the brightness:** R3 = 150 Ω, R4 = 560 Ω, R5 = 3.9 kΩ, R6 = 100 Ω, R7 = 82 Ω, R8 = 100 Ω. These replace the schematic's 270 Ω and the earlier all-red 680 / 100 Ω plan. The CMOS output pulls low much harder than it drives high, and the colours differ a lot in efficiency.
- **Timing uses the 100k / 10k / 10 µF set** (R1 / R2 / C1), with the same blink rate. With R2 = 1 kΩ, R2 drew about 3 mA from the cell while the white LED was lit, and the white needs every bit of cell voltage.
- **C1's footprint is non-polar and has no "+" mark.** The electrolytic's + lead goes in pad 1 (connected to U1 pins 2 and 6), and the − lead goes in pad 2 (GND).
- **Avoid eBay/AliExpress "TLC555" or "7555" lots.** They're often relabelled bipolar NE555s that fail at 3 V.
