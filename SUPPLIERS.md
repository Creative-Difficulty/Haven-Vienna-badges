# Suppliers — Haven Vienna badges

One LCSC order covers everything for 75 badges plus 5 spare sets. The only thing not in it is the CR2032 cells, which are handled separately.

Prices are LCSC USD prices without VAT, checked on **2026-10-26**. Re-check stock before ordering.

## Order (LCSC)

| Ref | Part | LCSC | Buy | Unit | Total |
|---|---|---|---|---|---|
| U1 | XINLUDA **XD551**, CMOS 555 (TLC555 clone), DIP-8 | [C707092](https://www.lcsc.com/product-detail/C707092.html) | 80 | $0.1248 | $9.98 |
| BT1 | MYOUNG **BS-07-A1BJ001**, CR2032 holder | [C2979167](https://www.lcsc.com/product-detail/C2979167.html) | 80 | $0.3199 | $25.59 |
| SW1 | Kinghelm KH-6X6X5H-TJ, 6×6×5 mm tactile switch | [C2837515](https://www.lcsc.com/product-detail/C2837515.html) | 100 | $0.0168 | $1.68 |
| D1–D6 | Guiguang 5A2RUD, 5 mm red, 400–600 mcd, 45° | [C52034660](https://www.lcsc.com/product-detail/C52034660.html) | 460 | $0.0183 | $8.42 |
| R3–R5 | 680 Ω, ¼ W carbon film (UNI-ROYAL CFR0W4J0681A50) | [C70784](https://www.lcsc.com/product-detail/C70784.html) | 250 | $0.0125 | $3.12 |
| R6–R8 | 100 Ω, ¼ W metal film (UNI-ROYAL MFR0W4F1000A50) | [C57438](https://www.lcsc.com/product-detail/C57438.html) | 250 | $0.0141 | $3.52 |
| R1 | 10 kΩ, ¼ W carbon film (UNI-ROYAL CFR0W4J0103A50) | [C61299](https://www.lcsc.com/product-detail/C61299.html) | 100 | $0.0123 | $1.23 |
| R2 | 1 kΩ, ¼ W carbon film (UNI-ROYAL CFR0W4J0102A50) | [C66649](https://www.lcsc.com/product-detail/C66649.html) | 100 | $0.0134 | $1.34 |
| C1 | 100 µF 16 V electrolytic, 6.3×5 mm, 2.5 mm pitch (Huawei KF1C101ME050A00CV0) | [C216305](https://www.lcsc.com/product-detail/C216305.html) | 80 | $0.0340 | $2.72 |
| | | | | **Parts** | **$57.61** |

Quantities are rounded up to LCSC's order steps (20 or 50 for most parts). The parts weigh about 0.6 kg.

### Total cost

LCSC charges the 20 % Austrian VAT at checkout, on parts and shipping together. At 1 USD ≈ €0.89:

| Shipping | Total incl. VAT | In EUR | Per badge |
|---|---|---|---|
| $10 | $81.14 | €72 | €0.96 |
| $25 | $99.14 | €88 | €1.18 |
| $35 | $111.14 | €99 | €1.32 |

The order stays under €100 as long as shipping is under about **$35**. Check this at checkout before paying.

**Shipping has to be express (DHL, UPS or FedEx).** The event is on 14 Nov. "Global Standard Direct Line" is cheaper, but it takes 1–3 weeks, which is too slow. Order this week.

## Why these parts

- **U1, XD551 instead of XD7555.** Both are CMOS 555s that run from 2 V. The XD7555 (ICM7555 type) drives its output high weakly: its datasheet curves show roughly 600 Ω at 3 V. D4–D6, which the output drives high, would barely light. LCSC also has only 80 in stock. The XD551 copies the TI TLC555's output stage and is about 2.5× stronger. It's also cheaper, with 690 in stock.
- **BT1:** The footprint has 2 pins 20.8 mm apart in 1.5 mm holes, which matches this exact holder. The cheaper LCSC holders (BS-02, BS-04, LOTES AAA-BAT-029, …) have 20.0 mm pitch or are vertical, so they don't fit. This holder is 44 % of the parts cost, and there's no drop-in alternative.
- **D1–D6:** These are AlGaInP red LEDs with a low forward voltage of about 1.75 V at low current, which suits a 3 V cell. They are brighter and cheaper than the Everlight 333-2SURD. The leads are 15.5 mm long, which is fine for a 1.6 mm board.
- **R3–R8: 680 Ω / 100 Ω instead of the schematic's 270 Ω.** We decided this on 2026-10-26; see "Electrical check".
- **R1, R2, C1:** These are the schematic's timing values. The capacitor is 6.3 mm × 5 mm with 2.5 mm pitch, the same size as the footprint, so it sits flat on the back. The 100k/10k/10 µF alternative would only save battery, and that doesn't matter because the badge only runs while the button is pressed.
- **SW1:** A standard 6×6 mm 4-pin tactile switch with 6.5 × 4.5 mm pin spacing. It only fits the footprint in the correct orientation.

## Electrical check (3 V CR2032, XD551)

- **Oscillator:** R2 = 1k (from + to DIS), R1 = 10k (DIS to THR), C1 = 100 µF. That gives about 0.7 Hz: D4–D6 are on for about 0.76 s, then D1–D3 for about 0.69 s.
- **LED drive:** D1–D3 hang from + and the output pulls them low. D4–D6 go to GND and the output drives them high. At 3 V the output's low side is roughly 45 Ω and its high side roughly 260 Ω (estimated from the datasheet's 2 V and 5 V figures).
  - With 270 Ω everywhere, D1–D3 would get about 2.6 mA and D4–D6 about 1.1 mA, so half the badge would be visibly dimmer.
  - With 680 Ω on R3–R5 and 100 Ω on R6–R8, each LED gets about 1.3–1.4 mA. With these LEDs that's about 25–40 mcd each, clearly visible indoors.
- **Battery:** The badge draws about 4–7 mA while the button is held. CR2032s handle that fine for this kind of push-to-blink use.
- **Leaving out the CV cap and supply decoupling is fine with a CMOS 555.** RESET is tied to +. In each half of the cycle, the off LEDs see 0 V across them.

## Assembly notes

- **C1 polarity isn't marked on the board.** The footprint is non-polar and has no "+". The **long lead (+) goes in pad 1**, which connects to U1 pins 2 and 6. The **striped lead (−) goes in pad 2**, the GND pad tied to the ground fill with thermal spokes. If it goes in backwards, the capacitor leaks and the blinking slows down or stops.
- **R3, R4, R5 = 680 Ω** (they go with D1–D3) and **R6, R7, R8 = 100 Ω** (with D4–D6). Resistor values are only on the Fab layer, so nothing printed on the board contradicts this. Hand the people soldering this list anyway.
- U1, C1 and BT1 go on the **back**. U1 pin 1 is the rounded-square pad.
- LEDs: the square pad is the cathode (short leg, flat side).
- **Solder one badge as soon as the parts arrive,** before building the rest. Check that both LED groups light about equally while the button is held. The XD551 is a clone; it comes from LCSC, not an eBay lot, but it isn't specified at exactly 3 V.

## Backups (if something sells out)

| Ref | Part | LCSC | Note |
|---|---|---|---|
| U1 | XINLUDA XD555 (TS555 clone, specified at 3 V) | [C521185](https://www.lcsc.com/product-detail/C521185.html) | 265 in stock, $0.134. Its output is a bit weaker than the XD551's. |
| U1 | XINLUDA XD7555 | [C521188](https://www.lcsc.com/product-detail/C521188.html) | Only 80 in stock. D4–D6 would be dim even with 100 Ω. |
| D1–D6 | Everlight 333-2SURD/S530-A3 | [C87271](https://www.lcsc.com/product-detail/C87271.html) | $0.0262 at 500+, 200 mcd, diffused. |
| SW1 | SHOU HAN SH-6X6X5H-STM | [C22383475](https://www.lcsc.com/product-detail/C22383475.html) | Same size. |
| C1 | AISHI EH71CM101E07OT (100 µF 16 V, 6.3×7 mm) | [C112487](https://www.lcsc.com/product-detail/C112487.html) | 2 mm taller, $0.024. |
| R* | UNI-ROYAL MFR (metal film) or CFR (carbon film) in the same value | — | All are 6.5 × 2.2 mm bodies that fit the 7.62 mm pitch. |

There is no backup for BT1. LCSC had 1,340 in stock.

## Rejected

- Genuine TI TLC555CP from Reichelt.at (€1.00), Bürklin (€0.57 + €8.30 shipping) and Mouser (~€0.73) cost too much. On LCSC the TLC555CP (C910886) is out of stock and the TLC555IP (C1520182) has 3 left.
- eBay and AliExpress "TLC555"/"7555" lots are often relabelled bipolar NE555s, which don't work at 3 V.
- HGSEMI TLC555N, LMC555N and ICM7555N: LCSC lists them as 4.5–15 V, so they're not safe at 3 V.
