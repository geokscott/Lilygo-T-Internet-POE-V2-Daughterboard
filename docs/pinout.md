# Pinout (rev 1.0)

Transcribed from `docs/images/schematic-rev1.0.png`. Net names in the schematic
are shown as drawn. The ESP32 GPIO column is the assignment used by the firmware
variant `ttgo-t-internet-poe-v2-SX1278` in the LoRa_APRS_iGate fork.

## H1: 2x8 female header (mates with the T-Internet-POE V2)

| H1 pin | Net | ESP32 GPIO |
|-------:|-----|-----------:|
| 1 | 3V3 | - |
| 2 | GND | - |
| 3 | 3V3 | - |
| 4 | GND | - |
| 5 | IO2 | 2 |
| 6 | SDA (BME280) | 14 |
| 7 | NSS (RA-02) | 4 |
| 8 | SCL (BME280) | 15 |
| 9 | SCK (RA-02) | 33 |
| 10 | IO12 | 12 |
| 11 | RESET (RA-02) | 16 |
| 12 | MOSI (RA-02) | 32 |
| 13 | MISO (RA-02) | 34 |
| 14 | DIO0 (RA-02) | 35 |
| 15 | IO36 | 36 |
| 16 | IO39 | 39 |

GPIO 14 and 15 (I2C) are shared with the T-Internet-POE's microSD slot, so
they are only free when no microSD card is used. GPIO 15 is also an ESP32
strapping pin; normal I2C pull-ups are harmless.

Odd pins are the right-hand column of the symbol (1, 3, ... 15), even pins the
left-hand column (2, 4, ... 16), as drawn in the schematic.

## J1: 1x6 male header (breakout)

| J1 pin | Net |
|-------:|-----|
| 1 | 3V3 |
| 2 | GND |
| 3 | IO2 |
| 4 | IO12 |
| 5 | IO36 |
| 6 | IO39 |

J1 pins 3-6 are the same nets as H1 pins 5, 10, 15, 16.

## On-board modules

- **RA-02 (SX1278):** GND, 3V3, RESET, DIO0, NSS, MOSI, MISO, SCK connected; DIO1-DIO5 unconnected.
- **BME280:** 3V3, GND, SCL, SDA connected (I2C).

