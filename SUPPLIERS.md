# Suppliers — Haven Vienna badges

One LCSC order covers everything for 75 badges plus 5 spare sets. The only thing not in it is the CR2032 cells, which are handled separately.

Prices are LCSC USD prices without VAT, checked on **2026-10-27**. Re-check stock before ordering.

## LED colours

Each badge has 1 green, 1 white, 2 orange and 2 red LEDs, all from the same Guiguang 5 mm, 45° family. Every LED has its own resistor, so the PCB doesn't change; only the resistor values do.

| LED | On the front print | Colour | Part | Resistor |
|---|---|---|---|---|
| D1 | orange tree, left | green (lime, 570 nm) | 5A2YGUC | R3 = 150 Ω |
| D2 | orange tree, middle | orange | 5A2OUD | R4 = 560 Ω |
| D3 | top of the tree, next to the white "haven" lettering | white | 5A2WUC | R5 = 3.9 kΩ |
| D4 | flower beside the red "HACK CLUB" banner | red | 5A2RUD | R6 = 100 Ω |
| D5 | middle of the big yellow flower | orange | 5A2OUD | R7 = 82 Ω |
| D6 | flower at the right edge | red | 5A2RUD | R8 = 100 Ω |

The tree trio (green, orange, white) and the flower trio (red, orange, red) blink alternately.

**Why white and green are in the tree:** D1–D3 hang from + and the 555 output pulls them to ground, which it does strongly. D4–D6 are driven by the output going high, which is weak at 3 V and only works for low-voltage LEDs.

- **White** needs about 2.5 V of the cell's 3 V. In D4–D6 it wouldn't light at all.
- **Green** is the least efficient colour, so it needs about 4–5 mA to keep up with the others. Only the strong side can supply that through a resistor.
- I also tried the green on the flower side. There it needs a 0 Ω link, and the whole flower trio's balance then depends on that one LED's tolerance. It also makes all six LEDs about 40 % dimmer.

## Order (LCSC)

| Ref | Part | LCSC | Buy | Unit | Total |
|---|---|---|---|---|---|
| U1 | XINLUDA **XD551**, CMOS 555 (TLC555 clone), DIP-8 | [C707092](https://www.lcsc.com/product-detail/C707092.html) | 80 | $0.1248 | $9.98 |
| BT1 | MYOUNG **BS-07-A1BJ001**, CR2032 holder | [C2979167](https://www.lcsc.com/product-detail/C2979167.html) | 80 | $0.3199 | $25.59 |
| SW1 | Kinghelm KH-6X6X5H-TJ, 6×6×5 mm tactile switch | [C2837515](https://www.lcsc.com/product-detail/C2837515.html) | 100 | $0.0168 | $1.68 |
| D1 | Guiguang **5A2YGUC**, 5 mm lime green 570 nm, clear lens, 100–200 mcd | [C52034652](https://www.lcsc.com/product-detail/C52034652.html) | 100 | $0.0304 | $3.04 |
| D2, D5 | Guiguang **5A2OUD**, 5 mm orange 605 nm, orange lens, 400–600 mcd | [C52034656](https://www.lcsc.com/product-detail/C52034656.html) | 200 | $0.0277 | $5.54 |
| D3 | Guiguang **5A2WUC**, 5 mm white, clear lens, 10–14 cd | [C52034716](https://www.lcsc.com/product-detail/C52034716.html) | 100 | $0.0249 | $2.49 |
| D4, D6 | Guiguang **5A2RUD**, 5 mm red 625 nm, red lens, 400–600 mcd | [C52034660](https://www.lcsc.com/product-detail/C52034660.html) | 200 | $0.0183 | $3.66 |
| R3 | 150 Ω, ¼ W carbon film (UNI-ROYAL CFR0W4J0151A50) | [C70814](https://www.lcsc.com/product-detail/C70814.html) | 100 | $0.0119 | $1.19 |
| R4 | 560 Ω, ¼ W carbon film (UNI-ROYAL CFR0W4J0561A50) | [C70791](https://www.lcsc.com/product-detail/C70791.html) | 100 | $0.0126 | $1.26 |
| R5 | 3.9 kΩ, ¼ W metal film (UNI-ROYAL MFR0W4F3901A50) | [C58654](https://www.lcsc.com/product-detail/C58654.html) | 100 | $0.0128 | $1.28 |
| R6, R8 | 100 Ω, ¼ W carbon film (UNI-ROYAL CFR0W4J0101A50) | [C61287](https://www.lcsc.com/product-detail/C61287.html) | 200 | $0.0143 | $2.86 |
| R7 | 82 Ω, ¼ W carbon film (UNI-ROYAL CFR0W4J0820A50) | [C70820](https://www.lcsc.com/product-detail/C70820.html) | 100 | $0.0126 | $1.26 |
| R1 | 100 kΩ, ¼ W carbon film (UNI-ROYAL CFR0W4J0104A50) | [C61303](https://www.lcsc.com/product-detail/C61303.html) | 100 | $0.0125 | $1.25 |
| R2 | 10 kΩ, ¼ W carbon film (UNI-ROYAL CFR0W4J0103A50) | [C61299](https://www.lcsc.com/product-detail/C61299.html) | 100 | $0.0123 | $1.23 |
| C1 | 10 µF 50 V electrolytic, 5×7 mm, 2.0 mm pitch (Huawei KS1H100MC070A00CV0) | [C216326](https://www.lcsc.com/product-detail/C216326.html) | 80 | $0.0304 | $2.43 |
| (R5 tuning) | 2.7 kΩ, ¼ W metal film (UNI-ROYAL MFR0W4F2701A50) | [C58615](https://www.lcsc.com/product-detail/C58615.html) | 100 | $0.0135 | $1.35 |
| (R5 tuning) | 5.6 kΩ, ¼ W carbon film (UNI-ROYAL CFR0W4J0562A50) | [C70764](https://www.lcsc.com/product-detail/C70764.html) | 100 | $0.0087 | $0.87 |
| | | | | **Parts** | **$66.97** |

Quantities are rounded up to LCSC's order steps. For red and orange, 200 costs less than 160 because of the price break at 200. The parts weigh about 0.65 kg.

LCSC has only **200** of the 3.9 kΩ resistor. If they're gone, use 3.3 kΩ ([C61296](https://www.lcsc.com/product-detail/C61296.html)): the white comes out about 15 % brighter.

### Total cost

LCSC charges the 20 % Austrian VAT at checkout, on parts and shipping together. At 1 USD ≈ €0.89:

| Shipping | Total incl. VAT | In EUR | Per badge |
|---|---|---|---|
| $10 | $92.36 | €82 | €1.10 |
| $25 | $110.36 | €98 | €1.31 |
| $35 | $122.36 | €109 | €1.45 |

**The order stays under €100 only if shipping is under about $26.** With the all-red LEDs it was $35; the extra colours add about $8. If checkout shows more, drop the two tuning resistors ($2.22) and order 75 holders and 555s instead of 80 (about $2.20 less).

**Shipping has to be express (DHL, UPS or FedEx).** The event is on 14 Nov. "Global Standard Direct Line" is cheaper, but it takes 1–3 weeks, which is too slow. Order this week.

## What the new colours change

- **White can't be guaranteed to match the others. With a 3 V cell and this PCB, nothing fixes that.**
  - The white LED needs about 2.4–2.6 V of the 3 V, so its current depends on the cell voltage and on the LED's own forward voltage. The datasheet allows 2.8–3.2 V at 20 mA.
  - R5 is chosen so the white matches the others on a fresh cell. Badges only run while the button is held, so the cells stay fresh through the event.
  - Between badges, whites will still range from about half as bright to about 1.5× as bright as the other LEDs.
  - As a cell runs down, white fades first (see the table below).
- **The white is a cold 11,000–13,000 K white** and looks slightly bluish next to the print's white lettering. Warmer whites are less efficient, so they'd need more current and would suffer even more from the voltage problem.
- **The green is lime (570 nm), not emerald (525 nm).** An emerald green has the same voltage problem as white. Lime also matches the badge's lime background.
  - Lime is the least efficient colour (100–200 mcd at 20 mA, against 400–600 for red and orange), so D1 runs at about 4.5 mA. That's well within the LED's 20 mA rating and the 555's output rating.
  - Of the two lime parts, the green-lens 5A2YGUD only reaches 40–60 mcd, so the clear 5A2YGUC is used.
- **Lenses differ when the LEDs are off.** Red and orange have tinted lenses; green and white are water clear. When lit, all six have the same 45° beam.
- **The timing values switch to the 100k / 10k / 10 µF set.** It gives the same 0.7 Hz blink. With R2 = 1 kΩ, about 3 mA flowed from + into the 555's discharge pin while the tree trio was lit, and that pulled the cell voltage down just when the white LED needs it most. CLAUDE.md already allows either set.
- **No other side effects:**
  - The off LEDs never see enough voltage to glow faintly.
  - Every LED stays far below its current rating.
  - The cell supplies about 4.5–7.5 mA while the button is held.

### Brightness (mcd, estimated)

| Condition | D1 green | D2 orange | D3 white | D4 red | D5 orange | D6 red |
|---|---|---|---|---|---|---|
| Fresh cell | 39 | 41 | 43 | 37 | 36 | 37 |
| Typical | 33 | 35 | 29 | 33 | 32 | 33 |
| Tired cell (2.85 V) | 27 | 30 | 16 | 28 | 27 | 28 |
| Nearly flat (2.75 V) | 23 | 26 | 8 | 25 | 23 | 25 |
| Fresh cell, white at top of its voltage range | 39 | 41 | 26 | 37 | 36 | 37 |
| Fresh cell, white at bottom of its voltage range | 39 | 41 | 62 | 37 | 36 | 37 |
| Weak 555 output | 29 | 32 | 20 | 23 | 21 | 23 |
| Strong 555 output | 36 | 38 | 36 | 43 | 43 | 43 |

These figures come from a circuit simulation using the datasheet's typical values. The 555's output strength at 3 V is estimated, because its datasheet only covers 2 V and 5 V.

Apart from the white, the five coloured LEDs stay within about 15 % of each other. Depending on the actual 555 parts, the tree trio and the flower trio can differ from each other by up to about 25 %.

## Why these parts

- **U1, XD551 instead of XD7555.** Both are CMOS 555s that run from 2 V. The XD7555 (ICM7555 type) drives its output high weakly: its datasheet curves show roughly 600 Ω at 3 V. D4–D6, which the output drives high, would barely light. LCSC also has only 80 in stock. The XD551 copies the TI TLC555's output stage and is about 2.5× stronger. It's also cheaper, with 690 in stock.
- **BT1:** The footprint has 2 pins 20.8 mm apart in 1.5 mm holes, which matches this exact holder. The cheaper LCSC holders (BS-02, BS-04, LOTES AAA-BAT-029, …) have 20.0 mm pitch or are vertical, so they don't fit. This holder is 39 % of the parts cost, and there's no drop-in alternative.
- **LEDs:** One family (Guiguang 5A2…) for all colours, so they share the same 5 mm, 45° package and 15.5 mm leads.
  - Red, orange and lime are AlGaInP parts with about 1.8 V forward voltage, which suits a 3 V cell.
  - The white is the family's most efficient part. That matters: the less current it needs, the less voltage it needs.
- **R1, R2, C1:** the 100k / 10k / 10 µF timing set. C1 is 5 mm wide with 2.0 mm pitch; bend the leads slightly to fit the 2.5 mm holes.
- **SW1:** A standard 6×6 mm 4-pin tactile switch with 6.5 × 4.5 mm pin spacing. It only fits the footprint in the correct orientation.

## Electrical check (3 V CR2032, XD551)

- **Oscillator:** R2 = 10k (from + to DIS), R1 = 100k (DIS to THR), C1 = 10 µF. That gives about 0.7 Hz: the flower trio is on for about 0.76 s, then the tree trio for about 0.69 s.
  - C1's leakage at 3 V is far below the roughly 10 µA charging current, so it doesn't affect the timing.
- **LED drive:** At 3 V the output's low side is roughly 45 Ω and its high side roughly 260 Ω. The resistor values above even out that difference as well as the colours' different efficiencies.
- **Battery:** The badge draws about 4.5–7.5 mA while the button is held. CR2032s handle that fine for push-to-blink use.
- **Leaving out the CV cap and supply decoupling is fine with a CMOS 555.** RESET is tied to +.

## Assembly notes

- **The resistor values differ per LED.** Values are only on the Fab layer, so nothing printed on the board helps. Hand the people soldering this list:

  | Ref | R1 | R2 | R3 | R4 | R5 | R6 | R7 | R8 |
  |---|---|---|---|---|---|---|---|---|
  | Value | 100 kΩ | 10 kΩ | 150 Ω | 560 Ω | 3.9 kΩ | 100 Ω | 82 Ω | 100 Ω |
  | Bands | brown-black-yellow | brown-black-orange | brown-green-brown | green-blue-brown | orange-white-black-brown-brown (5 bands, metal film) | brown-black-brown | grey-red-black | brown-black-brown |

- **Each LED colour has a fixed position:** D1 green, D2 orange, D3 white, D4 red, D5 orange, D6 red.
- **C1 polarity isn't marked on the board.** The footprint is non-polar and has no "+".
  - The **long lead (+) goes in pad 1**, which connects to U1 pins 2 and 6.
  - The **striped lead (−) goes in pad 2**, the GND pad tied to the ground fill with thermal spokes.
  - If it goes in backwards, the capacitor leaks and the blinking slows down or stops.
- U1, C1 and BT1 go on the **back**. U1 pin 1 is the rounded-square pad.
- LEDs: the square pad is the cathode (short leg, flat side).
- **White and green LEDs are sensitive to static.** Touch something grounded before handling them.
- **Solder one badge as soon as the parts arrive,** before building the rest, with a fresh cell. Then:
  - Compare the white to the other five. If it's clearly brighter, use 5.6 kΩ for R5; if clearly dimmer, use 2.7 kΩ.
  - Also check that the two trios look about equally bright.
  - The XD551 is a clone; it comes from LCSC, not an eBay lot, but it isn't specified at exactly 3 V.

## Backups (if something sells out)

| Ref | Part | LCSC | Note |
|---|---|---|---|
| U1 | XINLUDA XD555 (TS555 clone, specified at 3 V) | [C521185](https://www.lcsc.com/product-detail/C521185.html) | 265 in stock, $0.134. Its output is a bit weaker than the XD551's. |
| U1 | XINLUDA XD7555 | [C521188](https://www.lcsc.com/product-detail/C521188.html) | Only 80 in stock. The flower trio would be dim. |
| D1 | Guiguang 5A4YGUC | [C52034653](https://www.lcsc.com/product-detail/C52034653.html) | Same LED with longer leads. |
| D2, D5 | Guiguang 5A4OUD | [C52034657](https://www.lcsc.com/product-detail/C52034657.html) | Same LED with longer leads. |
| D3 | Guiguang 5A4WUC | [C52034717](https://www.lcsc.com/product-detail/C52034717.html) | Same LED with longer leads. |
| D4, D6 | Guiguang 5A4RUD | [C52034661](https://www.lcsc.com/product-detail/C52034661.html) | Same LED with longer leads. |
| R5 | 3.3 kΩ (UNI-ROYAL CFR0W4J0332A50) | [C61296](https://www.lcsc.com/product-detail/C61296.html) | White about 15 % brighter. |
| SW1 | SHOU HAN SH-6X6X5H-STM | [C22383475](https://www.lcsc.com/product-detail/C22383475.html) | Same size. |
| C1 | Huawei KF1E100MB050A00CV0 (10 µF 25 V, 4×5 mm, 1.5 mm pitch) | [C216306](https://www.lcsc.com/product-detail/C216306.html) | Leads need bending to 2.5 mm. |
| R* | UNI-ROYAL MFR (metal film) or CFR (carbon film) in the same value | — | All are 6.5 × 2.2 mm bodies that fit the 7.62 mm pitch. |

There is no backup for BT1. LCSC had 1,340 in stock.

## Rejected

- Genuine TI TLC555CP from Reichelt.at (€1.00), Bürklin (€0.57 + €8.30 shipping) and Mouser (~€0.73) cost too much. On LCSC the TLC555CP (C910886) is out of stock and the TLC555IP (C1520182) has 3 left.
- eBay and AliExpress "TLC555"/"7555" lots are often relabelled bipolar NE555s, which don't work at 3 V.
- HGSEMI TLC555N, LMC555N and ICM7555N: LCSC lists them as 4.5–15 V, so they're not safe at 3 V.
- Emerald green (Guiguang 5A2GUD, 525 nm): needs about 2.5 V, so it has the same voltage problem as white.
- The 120 Ω resistor (UNI-ROYAL CFR and MFR) is out of stock, so the flower trio uses 100 Ω / 82 Ω / 100 Ω instead.
