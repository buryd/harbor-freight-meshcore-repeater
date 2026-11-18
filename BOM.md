# Harbor Freight MeshCore Repeater — Bill of Materials

One solar MeshCore repeater built around a Seeed Studio XIAO nRF52840 and Wio-SX1262, housed in a Harbor Freight solar security light. Assembly steps are in [BUILD.md](BUILD.md). Ham Radio Crusader builds this parts list in [Let's Build a Meshcore Repeater](https://www.youtube.com/watch?v=Fqu7j6yl4KA).

Prices were taken from the product pages on 18 November 2026. They exclude tax and shipping, and store prices change.

**Cash to buy one of each package: $48.14**

Several packages contain more than one repeater uses. A second repeater needs another radio kit and another solar light. The antenna pack, wire, and brushes already cover more than one build.

## Buy list

| Line | Buy | Used on this repeater | Item | Source | Part number | Price |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | 1 kit | 1 kit | XIAO nRF52840 & Wio-SX1262 Kit for Meshtastic | [Seeed Studio](https://www.seeedstudio.com/XIAO-nRF52840-Wio-SX1262-Kit-for-Meshtastic-p-6400.html) | SKU 102010710 | $13.49 |
| 2 | 1 | 1 | Bunker Hill Security 115 Lumen Wall-Mount Solar Security Light, black | [Harbor Freight](https://www.harborfreight.com/115-lumen-wall-mount-solar-security-light-black-56252.html) | SKU 56252 | $14.99 |
| 3 | 1 pack of 2 | 1 antenna and 1 pigtail | Kaunosta 915 MHz LoRa antenna, 3 dBi, SMA male, with U.FL / MHF1 pigtail | [Amazon](https://www.amazon.com/dp/B0FDWFT1DH) | ASIN B0FDWFT1DH, model XF-A-7307 | $9.99 |
| 4 | 1 kit | A few inches of red and black | BNTECHGO 26 AWG silicone wire, 10 ft red and 10 ft black, 30-strand tinned copper | [Amazon](https://www.amazon.com/dp/B01CQJKC6E) | ASIN B01CQJKC6E, SW26G3008F10C2 | $6.68 |
| 5 | 1 pack of 36 | 1 brush | HFT 1/2 in. horsehair bristle acid shop brushes | [Harbor Freight](https://go.harborfreight.com/sku/61880/) | SKU 61880 (also 41338, 61264) | $2.99 |
| | | | | | **Package total** | **$48.14** |

Short links from the build notes, if the pages above move:

- Radio kit: https://tinyurl.com/Seeed-nRF-XIAO
- Solar light: https://tinyurl.com/HF-Solar-Light
- Antenna: https://tinyurl.com/SMA-Antenna
- Wire: https://tinyurl.com/soft-wire-26g
- Brushes: https://tinyurl.com/Parts-Brush

## What each line contributes

**1. Radio kit — $13.49.** Nordic nRF52840 (Bluetooth 5.0) plus Semtech SX1262 LoRa, 862–930 MHz. The kit contains the XIAO nRF52840, the Wio-SX1262 extension board, and one small LoRa antenna. USB-C input is 5 V. The battery pad input is rated 4.2 V. Standby current is listed under 5 µA. This board is the repeater. The small antenna that ships in the kit stays as a spare once the SMA antenna is fitted. The SX1262 in this kit is for the XIAO nRF52840.

**2. Solar light — $14.99.** Weatherproof housing and the power source. Size is about 4.87 × 3.75 × 1.91 in. The owner’s manual for UPC 792363562522 lists the internal cell as **3.7 V, 1200 mAh Li-ion**. The solar panel, cell, and housing come with the light, so they are not separate purchases. The LED lamp and motion sensor are the parts removed to make room for the radio. Harbor Freight ships this SKU only inside the 48 contiguous states. The cell is a lithium-ion battery: recycle it, and follow the manual (do not open, crush, or heat it above 140°F).

**3. SMA antenna — $9.99 for two.** US-band antenna, 900–930 MHz, 3 dBi, 50 ohm, SMA male, about 7.7 in (19.5 cm). Each pack includes two antennas and two U.FL-to-SMA-female pigtails (about 5.9 in / 15 cm). One repeater uses one antenna and one pigtail. The pigtail is what mates the Wio-SX1262 IPEX connector to an external SMA antenna. Fit the antenna before the radio transmits.

**4. 26 AWG silicone wire — $6.68.** 20 ft total (10 ft red, 10 ft black). Silicone jacket, 30 × 0.08 mm tinned strands, about 1.5 mm outside diameter, rated 600 V, flexible from −60°C to 200°C. Red and black are the battery and solar leads inside the housing. One repeater uses a few inches.

**5. Horsehair brushes — $2.99.** 36 brushes, 1/2 in. wide, about 6-1/8 in. long, metal handles. These are the flux brushes for the solder joints on the battery and solar leads. One repeater uses one brush.

## Already in the box

Bought with the two main parts. No extra line on the buy list.

| Comes with | Inside |
| --- | --- |
| Seeed kit | XIAO nRF52840 ×1, Wio-SX1262 ×1, small LoRa antenna ×1 |
| Solar light, SKU 56252 | Enclosure, solar panel, 3.7 V 1200 mAh Li-ion cell, charge circuit, LED lamp, peel-and-stick mount |

## Left over after one repeater

| Package | Left for the next build |
| --- | --- |
| Antenna 2-pack | 1 antenna and 1 pigtail |
| 26 AWG wire | Most of the 20 ft |
| Brush 36-pack | 35 brushes |

A second repeater adds one Seeed kit ($13.49) and one solar light ($14.99). The leftover antenna, wire, and brush cover that second radio.

## Reference list — Ham Radio Crusader “Meshcore Builds”

https://tinyurl.com/Meshcore-Builds

This is a public Amazon idea list of about 30 items for other MeshCore builds (other radios, larger panels, magnets, connectors). It is a reference shelf. This Harbor Freight repeater is the five lines above.

Items visible on that list on 18 November 2026, with the price shown that day:

| Item | Price shown | How it relates to this repeater |
| --- | --- | --- |
| FLY RC JST PH 2.0 mm 2-pin plugs, 20 pairs, 22 AWG | $7.69 | Optional battery connector |
| AreMe 90° USB-C male-to-female adapter, 2-pack | $5.99 | Optional, for programming the XIAO in a tight case |
| XHF adhesive-lined 3/8 in. heat shrink, 20 ft | $9.99 | Optional strain relief and sealing on splices |
| SOOCOOL Samsung 25R 3.7 V flat-top, 4-pack | $28.89 | Optional replacement cells. The light already includes a 1200 mAh cell |
| minidodoca USB-A 2-pin pigtail, 6 × 3.3 ft, 22 AWG | $9.99 | Optional power lead |
| ACOPOWER 10 W mono solar panel | $27.90 | Optional larger panel. This build uses the panel in the light |
| Bolt Dropper 12 in. UV zip ties, 100-pack | $11.63 | Optional mounting |
| MIKEDE neodymium cup magnets, 12-pack | $15.99 | Optional magnetic mount |
| FellDen 5 V 200 mA micro solar panels, 5-pack | — | Optional small panels |
| SEESII battery spot welder | $37.99 | Shop tool for building battery packs |
| Soshine 6 W 5 V solar panel, 2-pack | $33.99 | Optional larger panel |
| RAKwireless WisBlock US915 starter kit (RAK19007 + RAK4631) | $34.97 | Alternate radio. Replaces the Seeed kit |
| eifagur 915 MHz 5.8 dBi antenna with 10 ft cable | $32.99 | Alternate higher-gain antenna |
| DIYMAG rubber-coated magnets, M5 studs, 4-pack | $9.99 | Optional magnetic mount |
| Waveshare solar power manager, module D, 6–24 V | $19.19 | Optional charge controller for a larger panel |
| uxcell M16×1.5 cable glands, 4–8 mm, 10-pack | $7.79 | Optional sealed antenna or cable exit |
| Heltec T096 nRF52840 + SX1262 node | $44.99 | Alternate radio. Replaces the Seeed kit |
| MOOKEERF N-male to N-male adapter, 2-pack | $9.99 | Optional, for N-connector feedline |

The list page reported 30 items. Prices above are only the listings the page returned in full. Open the idea list for the rest and for current prices.
