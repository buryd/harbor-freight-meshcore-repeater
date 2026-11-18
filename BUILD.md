# Harbor Freight MeshCore Repeater — Construction

Build the repeater on the bench, then move the working radio into the solar light. Parts are listed in [BOM.md](BOM.md).

The Seeed kit arrives with Meshtastic installed. This repeater runs MeshCore repeater firmware. Power comes from the light’s 3.7 V, 1200 mAh cell. The 915 MHz whip mounts outside the case.

## Tools

These are shop tools. They are not on the buy list.

| Tool | Use |
| --- | --- |
| USB-C data cable | Flash and configure the XIAO. A charge-only cable will not work. |
| Soldering iron, solder, and flux | Battery leads. The horsehair brush from the buy list spreads the flux. |
| 26 AWG silicone wire, red and black | Power leads inside the case. A few inches is enough. |
| Multimeter | Identify the cell, the panel, and the lamp before any wire is cut. |
| 1/4-inch drill bit | SMA antenna hole. Confirm against the pigtail’s jack before drilling. |
| 1/8-inch drill bit | Drain hole. |
| Outdoor silicone | Seal the antenna hole. |
| Small pry tool | Open the light housing. |

Optional, from the [Meshcore Builds idea list](https://tinyurl.com/Meshcore-Builds): a right-angle USB-C adapter if the jack faces a wall of the case, and adhesive-lined heat shrink for the splices.

## Safety

The cell is a lithium-ion battery, 3.7 V, 1200 mAh, per the SKU 56252 owner’s manual (UPC 792363562522).

- Tape every joint. A loose strand across the cell terminals is a short.
- Unhook one side of the cell while soldering so a slip cannot short it through the iron.
- Stay under the manual’s 140°F limit. Recycle the cell when it is finished. The manual also says to avoid opening, crushing, or incinerating it.
- Snap an antenna onto the Wio-SX1262 U.FL jack before the radio transmits. An empty jack during transmit can damage the SX1262.
- Leave transmit power on the USA/Canada preset. This SX1262 tops out at +22 dBm, under the 30 dBm unlicensed limit on 902–928 MHz. This build adds no amplifier.

Harbor Freight has shipped more than one board inside SKU 56252. Identify every wire with the meter. Wire color is not a reliable guide.

## 1. Prove the radio on the USB cable

1. Stack the XIAO nRF52840 onto the Wio-SX1262 until both boards sit fully together.
2. Press the kit’s small LoRa antenna straight down onto the U.FL jack on the Wio board until it clicks. Press straight on. Prying the connector sideways tears the jack.
3. In Chrome or Edge, open the MeshCore flasher for this board: https://flasher.meshcore.io/seeed-studio-xiao-nrf52-wio/repeater
4. Connect the XIAO with the data cable.
5. Double-press the reset button beside the USB-C jack. A drive named `XIAO-SENSE` or `XIAO-BOOT` appears.
6. Flash the repeater firmware. On a new board, erasing first is appropriate. On a later update, skip a full erase so the repeater keeps its identity.

Configure the node at https://config.meshcore.io/ :

| Setting | Value |
| --- | --- |
| Firmware | MeshCore repeater build from the flasher link above |
| Preset | **USA/Canada (Recommended)** for the 915 MHz antenna |
| Radio plan | Leave the preset values. They are commonly 910.525 MHz, 62.5 kHz bandwidth, spreading factor 7, coding rate 5, inside 902–928 MHz. |
| Name | A place name you can recognize on the mesh |
| Location | Install coordinates |
| Admin password | Set one. The repeater can be administered over the mesh. |
| Transmit power | Leave the preset value |

Confirm the repeater shows up from a second MeshCore node before you open the light.

A 915 MHz antenna and the USA/Canada preset are the US/Canada pair. A different region needs that region’s preset and a matching antenna.

## 2. Open the light and separate the lamp from the power

The Bunker Hill case is about 4.87 × 3.75 × 1.91 in. Pry it open and photograph the wiring before cutting anything.

Find three circuits with the meter:

| What you measure | What it means |
| --- | --- |
| About 3.2–4.2 V across the cell. The higher side is positive. | Battery. This pair powers the radio. |
| A few volts across two wires, panel in sunlight, higher on one side. | Solar panel. Mark the positive wire. |
| The remaining wires | LED lamp. This is the load to remove. |

Leave the solar panel, the light’s charge board, and the cell connected to each other. Disconnect only the LED. At night that lamp would drain the 1200 mAh cell.

Put the panel in the sun for a few minutes with the LED disconnected. The cell voltage should creep up and settle near 4.2 V. That confirms the factory charger is still charging.

If the lamp and the charger are the same board, and lifting the lamp kills charging, skip the table in section 3 and use the alternate wiring at the end of that section.

## 3. Power the radio from the cell

Solder with the flux brush. Tin the pad, tin the wire, and tack it on quickly so the iron does not overheat the XIAO. Unhook one side of the cell while the iron is on a battery terminal. Insulate every joint with tape or heat shrink.

| From | To | Label on the XIAO |
| --- | --- | --- |
| Cell positive | Battery pad on the back, beside the USB-C jack | `BAT+` |
| Cell negative | Ground | `GND` |

Leave the pin marked `5V` empty. That pin is the charger input. With the cell on `BAT+` and `GND`, the radio runs from the battery and MeshCore can read the voltage. The light’s charger, already matched to this panel and this cell, keeps charging the cell.

The `GND` pad is the same net as pin 13 on the Wio header. The `5V` pad is the same net as pin 14. Use the silkscreen labels, then confirm with the meter.

Before the cell is reconnected, check the leads again:

- `BAT+` to `GND` reads about 3.2–4.2 V, positive on `BAT+`.
- The two leads are not shorted to each other.

### Alternate wiring

Use this path only after the light’s charge board has been removed because it was inseparable from the lamp.

1. Measure the panel in full sun with nothing else attached.
2. When that open-circuit voltage is about 5–6 V, connect panel positive to the pin marked `5V`.
3. Connect panel negative and cell negative to `GND`.
4. Connect cell positive to `BAT+`.

The XIAO’s charger then limits charge current to 50 or 100 mA, which suits this small panel. When the open-circuit panel voltage is above 6 V, keep that panel off the `5V` pin and put a separate one-cell solar charger between the panel and the cell. The Waveshare solar power module on the idea list is one such charger.

## 4. Move the antenna outside

1. Power the board off.
2. Unplug the kit antenna.
3. Press the U.FL end of the Kaunosta pigtail straight onto the same jack until it clicks.
4. Screw the SMA whip onto the other end of the pigtail.
5. Drill the case to fit the SMA jack. A bulkhead nut is usually a 1/4-inch hole. Check the connector before drilling.
6. Put the whip vertical, outside the plastic.
7. Seal the antenna hole with silicone.
8. Drill a separate drain about 1/8 inch at the lowest corner. Leave the drain open so water can leave.

Set the stacked boards where they cannot touch the battery springs or the LED reflector. Tape or a dab of hot glue holds them. The stack is about 21 × 18 mm, so it fits once the lamp hardware is out. Keep the USB-C jack reachable. A right-angle USB-C adapter helps in this shallow case.

The kit antenna stays as a spare.

## 5. Sun test, then mount

Close the case and leave it in full sun at ground level for several days. In the MeshCore app, the battery percentage should climb while the sun is on the panel and hold through the night.

The manual rates the cell at 3.7 V, 1200 mAh, and a charge from flat takes on the order of 10 hours of sun. A shaded eave will not keep this panel ahead of the radio.

Mount after both of these are true:

- Battery percentage holds through a few sunny days and the following nights.
- A second MeshCore node still hears the repeater.

Face the panel south in the northern hemisphere, with hours of direct sun, and above the snow line where snow piles up. The peel-and-stick pad holds the light on a clean surface. A screw or a zip tie is the better long-term mount once the case has been opened.

## Order of work

1. Flash MeshCore repeater firmware and confirm a second node hears it.
2. Open the light, photograph the wiring, and identify cell, panel, and lamp with the meter.
3. Disconnect the LED and confirm the cell still charges in the sun.
4. Solder the cell to `BAT+` and `GND`.
5. Swap the kit antenna for the external SMA pigtail, then seal the case and add the drain.
6. Soak-test at ground level.
7. Mount the panel toward the sun.
