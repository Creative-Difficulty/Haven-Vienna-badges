# Alternative suppliers (EU only) — Haven Vienna badges

This is a fallback to the LCSC order in `SUPPLIERS.md`. It uses only shops in the EU that deliver to Austria within a week: **Pollin** (Germany) and **Reichelt** (Germany). There are no customs and both ship in 2–5 working days.

**It does not fit the €100 budget. It costs about €195, roughly double.** Prices include 20 % VAT and were checked on **2026-10-26**.

## Why it can't fit €100

The 555 and the battery holder alone cost more than the whole budget:

- **CMOS 555 (DIP-8):** No EU shop sells the cheap clones (XD551, XD7555). The cheapest genuine part is the TI TLC555CP: **€0.85** at Pollin, €0.69 at Bürklin (business customers only), €1.00 at Reichelt. Mouser and Digi-Key are also around €0.85 incl. VAT.
- **CR2032 holder:** No EU shop sells the MYOUNG BS-07. The only close fit is the Wentronic KZH 20 at **€0.70**.

That's €1.55 per badge, or €116 for 75 badges, before LEDs, resistors, switches or shipping.

## Order

### Pollin — [pollin.at](https://www.pollin.at)

| Ref | Part | Pollin no. | Buy | Unit | Total |
|---|---|---|---|---|---|
| U1 | TI **TLC555CP**, CMOS 555, PDIP-8 | [101355](https://www.pollin.at/p/texas-instruments-tlc555cp-timer-c-mos-texas-instruments-101355) | 82 | €0.85 | €69.70 |

Pollin's shipping to Austria is normally **€6.99**. Until **Thursday 29 Oct** it is free above €69, which is why the order is 82 chips rather than 78: the 4 extra chips cost less than the shipping. After Thursday, buy 78 for €66.30 and pay the €6.99.

### Reichelt — [reichelt.at](https://www.reichelt.at)

| Ref | Part | Reichelt no. | Buy | Unit | Total |
|---|---|---|---|---|---|
| BT1 | Wentronic **KZH 20-1**, CR2032 holder (see fit notes) | [KZH 20-1](https://www.reichelt.at/at/de/shop/produkt/knopfzellenhalter_fuer_20_mm-44621) | 78 | €0.70 | €54.60 |
| D1–D6 | HuiYuan 5603R1C-KHC-B, 5 mm red, AlGaInP, 300–500 mcd, 90°, water clear | [5603R1C-KHC-B](https://www.reichelt.at/at/de/shop/produkt/led_5mm_bedrahtet_rot_500_mcd_90_-361959) | 470 | €0.05 | €23.50 |
| R3–R5 | 680 Ω, ¼ W carbon film (Yageo CFR-25) | [1/4W 680](https://www.reichelt.at/at/de/shop/produkt/widerstand_kohleschicht_680_ohm_0207_250_mw_5_-1460) | 240 | €0.018 | €4.32 |
| R6–R8 | 100 Ω, ¼ W carbon film (Yageo CFR-25) | [1/4W 100](https://www.reichelt.at/at/de/shop/produkt/widerstand_kohleschicht_100_ohm_0207_250_mw_5_-1336) | 240 | €0.021 | €5.04 |
| R1 | 10 kΩ, ¼ W carbon film (Yageo CFR-25) | [1/4W 10K](https://www.reichelt.at/at/de/shop/produkt/widerstand_kohleschicht_10_kohm_0207_250_mw_5_-1338) | 100 | €0.023 | €2.30 |
| R2 | 1 kΩ, ¼ W carbon film (Yageo CFR-25) | [1/4W 1,0K](https://www.reichelt.at/at/de/shop/produkt/widerstand_kohleschicht_1_0_kohm_0207_250_mw_5_-1315) | 100 | €0.021 | €2.10 |
| C1 | 100 µF 16 V electrolytic, 6.3 × 7 mm, 2.5 mm pitch | [SM 100/16RAD](https://www.reichelt.at/at/de/shop/produkt/subminiatur-elko_radial_100_f_16_v_rm_2_5_85_c_1000h_20_-25569) | 78 | €0.09 | €7.02 |
| SW1 | Diptronics DTS-62N, 6×6×5 mm tactile switch | [DIP DTS-62N](https://www.reichelt.at/at/de/shop/produkt/kurzhubtaster_printmontage_1_schliesser_6_x_6_x_5_mm-360044) | 78 | €0.25 | €19.50 |
| | | | | **Parts** | **€118.38** |

Reichelt ships to Austria by DPD for **€6.95**. Resistors are bought in 100s or more because Reichelt's price drops at 100 pieces.

### Total

| | |
|---|---|
| Pollin (82 × TLC555CP, free shipping until Thu) | €69.70 |
| Reichelt parts + shipping | €125.33 |
| **Total incl. VAT** | **€195.03** (€2.60 per badge) |

After Thursday it comes to €198.62.

**Ways to save a bit:**

- **About €7 less:** Reichelt's TASTER 3301 switch (€0.20, but Reichelt says only limited stock is left) and the Samwha 6.3 × 11.5 mm capacitor (€0.05, 4.5 mm taller on the back).
- **About €6 less:** TLC555CPs from [Bürklin](https://www.buerklin.com/en/p/49S5264) at €0.57 net (€0.69 incl. VAT), delivered in 1–2 days for €9.96. The page says the part is for business customers only.

Neither gets anywhere near €100.

## Fit and electrical notes

- **The holder isn't an exact match. Solder one first.** The KZH 20's pins are 20.5 mm apart; the footprint's are 20.8 mm. Its 0.7 mm pins still fit the 1.5 mm holes, each sitting about 0.15 mm off-center.
  - The + pin goes at the tab end, in pad 1. The body ends up about 1 mm further toward the − pad than a BS-07 would. I checked this against the PCB: it stays 0.7 mm inside the board edge (the BS-07 has 1.0 mm) and doesn't cover any pads.
  - The drawing shows short plastic studs under the base, and the board has no holes for them. The holder may sit about 1 mm high, or you clip the studs off.
- **The TLC555CP is the original TI part that the XD551 in `SUPPLIERS.md` copies.** So the 3 V analysis there still applies, including R3–R5 = 680 Ω and R6–R8 = 100 Ω. It's rated 2–15 V and 0–70 °C.
- **The LEDs are water clear rather than diffused, with a wide 90° beam.** At about 1.3 mA each they give roughly 20–30 mcd, similar to the LCSC choice. They're AlGaInP with a forward voltage around 1.8 V at low current, so 3 V is fine.
- **The switch fits:** DTS-6 parts use 6.5 × 4.5 mm pins, and the pins 6.5 mm apart are connected, which matches `SW_PUSH_6mm`.
- **The capacitor fits:** 6.3 mm diameter and 2.5 mm pitch, same as the footprint. It's 7 mm tall instead of 5 mm.
- The assembly notes in `SUPPLIERS.md` apply unchanged, including C1's unmarked polarity.

## Checked and rejected

- **Pollin's Goobay CR2032 holder (€0.69):** pins 22 mm apart. Doesn't fit.
- **Pollin's 6×6 switch:** 5.08 mm pin spacing. Doesn't fit.
- **Pollin's 10-pack of red LEDs:** no datasheet, so the forward voltage and brightness at 3 V are unknown.
- **Reichelt's cheaper LEDs at €0.05:** the 1000 mcd, 2000 mcd and 100 mcd ones aren't back in stock until 24 Nov 2026 or later.
- **Neuhold Elektronik (Graz):** has no CMOS 555. Its only CR2032 holder is €1.20. Its resistors are cheap (€1.20 per 100), but a third shipment cancels the saving.
- **TME, Farnell, RS, Conrad, Distrelec, Mouser and Digi-Key:** I couldn't check their prices live, because their sites block automated access. From search results, the TLC555CP is about €0.70–0.85 incl. VAT at each of them, so none of them would bring the total near €100.
