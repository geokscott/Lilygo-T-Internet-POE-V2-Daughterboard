# LilyGO T-Internet-POE V2 Daughterboard (RA-02 + BME280)

A small carrier PCB that plugs into the header of a **LilyGO T-Internet-POE V2** and adds:

- an **Ai-Thinker RA-02 (SX1278) 433 MHz LoRa module**, and
- a **BME280** temperature / humidity / pressure breakout.

It was designed to run the Ethernet (PoE) variant of
[richonguzman/LoRa_APRS_iGate](https://github.com/richonguzman/LoRa_APRS_iGate)
on the T-Internet-POE V2 (ESP32 + LAN8720). All parts are solder yourself; there are no SMD components on the board.

![PCB top](docs/images/pcb-top.png)

## Status

- Design revision: **1.0** (schematic dated 2026-11-22)
- Gerbers generated: **2026-11-22**
- Fabricated / tested: **not yet stated**

## What you need

| Part | Notes |
|------|-------|
| This PCB | Order from the Gerbers in [`fabrication/`](fabrication/) (see below) |
| LilyGO T-Internet-POE V2 | The board this plugs into: https://lilygo.cc/products/t-internet-poe |
| Ai-Thinker RA-02 (SX1278) 433 MHz module | Soldered to the PCB https://www.digikey.com/en/products/detail/ai-thinker/RA-02/16688840 |
| BME280 breakout (I2C) Optional | Soldered to the PCB, OR extended with pinheader; confirm your breakout's pin order matches the silkscreen https://protosupplies.com/product/bme280-i2c-pressure-humidity-temperature-sensor-module/ |
| 1x 2.54 mm 2x8 female header (H1) | Mates with the T-Internet-POE header |
| 1x 2.54 mm 1x6 male header (J1) Optional | Breaks out 3V3, GND, IO2, IO12, IO36, IO39 |

Breakout pinouts vary by vendor. Check yours against the schematic before soldering.

## Pinout

See [`docs/pinout.md`](docs/pinout.md). The schematic
([`docs/schematic/Lilygo-T-Internet-POE-V2-Daughterboard.pdf`](docs/schematic/Lilygo-T-Internet-POE-V2-Daughterboard.pdf)) is the
source of truth if the two ever disagree.

## Ordering the PCB

1. Take the zip in [`fabrication/`](fabrication/) (2 copper layers, silk, mask, outline and drill files).
2. Upload it to your PCB fab (e.g. JLCPCB) as a **bare board**. No assembly, BOM or pick-and-place files are needed.

## Firmware

Firmware support lives in the LoRa_APRS_iGate project, not here. The PlatformIO
environment for this hardware is `ttgo-t-internet-poe-v2-SX1278`
( future link to the upstream PR / fork branch once it exists).

## Other

- Use M2.5x11mm standoffs like these between the boards: https://www.amazon.com/dp/B08M3PN7BT
- The daughterboard mounts face up on the bottom of the Lilygo board.
- You can solder the BME280 on the daughterboard or solder horizontal pinheader for a remote sensor.
- J1 is optional, it there so you can access the unused IO ports in the future.
- (coming soon) I've included a 3D printable strain relief clamp for the U.FL conncted coaxial cable. It attaches to the PCB using the extra 2.5mm hole next to the Ra-02 chip.

## Files

```
fabrication/   Gerber + drill zip for rev 1.0, 3D print file for strain relief
docs/          pinout and images (schematic, PCB top/bottom)
```

The Gerbers, schematic and images are provided so the board can be built and its connections inspected.

## License

Licensed under the **CERN Open Hardware Licence Version 2 - Strongly
Reciprocal (CERN-OHL-S-2.0)**. See [`LICENSE`](LICENSE).

Source location: this repository.

## Credit

Designed by **George K Scott, K6GKS**.
