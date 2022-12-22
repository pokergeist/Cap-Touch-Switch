# Cap Switch Project

## Introduction

This project aims to create a capacitive touch switch that uses a CR2032 button cell to power a capacitive touch sensor and solid state relay to to assist with switch-adapting a device for assistive technology purposes.

## Status

| Date       | Status                   |
| ---------- | ------------------------ |
| 2022-12-21 | First posting. Untested. |

## Todo

* Test sensor power draw for the sensor and the LED in relay.
* Add on-off switch?
* Make sure SSR height (4mm) doesn't interfere with board mounting and sensor access.
* Compare the TTP223 and TTP223B.

### Components

| Component                          | Source                                                       | Specs                                                        |
| ---------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Capacitive touch sensor board (S1) | [HiLetgo TTP223 Cap Switch](https://smile.amazon.com/dp/B01D1D0FLG) (Amazon ) | 2.2-5.5V Toggle\|Momentary, Active High\|Low                 |
| Solid State Relay (K1)             | [Toshiba TLP241A](https://www.digikey.com/short/rw8vd8dn) ([datasheet](https://toshiba.semicon-storage.com/info/TLP241A_datasheet_en_20200217.pdf?did=14237&prodName=TLP241A)) | LED: 7.5mA Vf: 1.27V<br>Iout: 2A continuous, 6A pulsed<br>Ron: 90mΩ |
| Resistor 180Ω (R1) 1206            | [Stackpole 180Ω](https://www.digikey.com/short/m5wfc0cm)     | 1/4W 5% 1206                                                 |
| Coin Cell Holder (B1)              | [Keystone 1026](https://www.digikey.com/short/f35w9mv4) ([datasheet](https://www.keyelco.com/userAssets/file/M65p3.pdf)) | 4.5mm standoffs, (1) CR2032<br> or (2) CR2016 or 2025s       |
| CR2032 Coin Cells (B1)             |                                                              | Vnom: 3V                                                     |

## Mounting

The board is intended to be mounted with the cap sensor exposed. There are 3.5mm holes for securing with M3 screws or 3D printed posts.

On the bottom is a button cell holder for (2) CR2016 cells.

## Cap Touch Sensor

<img src="assets/cap_touch_sensor.png" alt="cap sensor" style="zoom:150%;" />

## Printed Circuit Board

## Top

<img src="assets/board_top.png" style="zoom:15%;" />

### Bottom

<img src="assets/board_bottom.png" alt="bottom" style="zoom:15%;" />