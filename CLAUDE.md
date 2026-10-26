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
- **LEDs:** **red** 5 mm. Yellow has less headroom from 3 V. Blue and white (forward voltage about 3 V) barely light.
- **R3–R5 = 680 Ω and R6–R8 = 100 Ω, not 270 Ω** (decided 2026-10-26). The CMOS output pulls low much harder than it drives high. With these values all six LEDs run at about 1.3 mA and look evenly bright.
- **Timing stays 10k / 1k / 100 µF.** The 100k / 10k / 10 µF alternative only saves battery, and that doesn't matter with a momentary switch.
- **C1's footprint is non-polar and has no "+" mark.** The electrolytic's + lead goes in pad 1 (connected to U1 pins 2 and 6), and the − lead goes in pad 2 (GND).
- **Avoid eBay/AliExpress "TLC555" or "7555" lots.** They're often relabelled bipolar NE555s that fail at 3 V.
