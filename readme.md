# Cap Switch Project

## Introduction

This project aims to create a capacitive touch switch that uses a CR2032 button cell to power a capacitive touch sensor and solid state relay to to assist with switch-adapting a device for assistive technology purposes.

## Status

|    Date    | Status                                                       |
| :--------: | ------------------------------------------------------------ |
| 2022-12-29 | Boards ordered.                                              |
| 2022-12-27 | Driver circuit simulated. Bench testing and transistor selection pending. |
| 2022-12-23 | Working to support multiple battery options.                 |
| 2022-12-21 | First posting. Untested.                                     |

**2022-12-27**

A current driver circuit has been selected. See board/[readme](#board/readme.md) file.

**2022-12-23**

I want to test some voltage regulation circuits to see so I can protect the SS Relay (<25mA) while reducing the current (and  power) draw toward the lower level and extending functionality over the range of whatever battery option is used.

## Todo

* Add on-off switch?
* Make sure SSR height (4mm) doesn't interfere with board mounting and sensor access.

## Mounting

The board is intended to be mounted with the cap sensor exposed. There are 3.5mm holes for securing with M3 screws or 3D printed posts.

On the bottom is a button cell holder for (2) CR2016 cells.

## Cap Touch Sensor

<img src="assets/cap_touch_sensor.png" alt="cap sensor" style="zoom:150%;" />

## Printed Circuit Board

Please refer to the board/[readme](board/readme.md) file for more info on the PCB.

### TTP223-BA6 Pinout & Modes

| Pin  | Function        |                                                              |
| :--: | --------------- | ------------------------------------------------------------ |
|  1   | Q               | Output pin (open drain).                                     |
|  2   | Vss (GND)       | Ground: 0V                                                   |
|  3   | I               | Input to Oscillator circuit.                                 |
|  4   | TOG (Jumper B)  | 1-Toggle or 0-Momentary mode.                                |
|  5   | Vdd (V+)        | Power: 2.0 - 5.5VDC                                          |
|  6   | AHLB (Jumper A) | Active 1-High or 0-Low output.                               |
|      | LPMB = 0        | Low Power Mode on. (Not Fast Mode)                           |
|      | MOTB = 1        | Max On Time 100s disabled. Infinite On if covered and detected. |
|      | SLRFTB = 1      | Sampling Rate: 1.6ms. Lower current and sensitivity.         |

### Board Jumpers

Leave Jumper A open for an Active High output unless you want to invert the operation of the relay.

Short Jumper B to switch from Momentary mode to Toggle mode.

## Run Time Calculations

| Item                                 | Capacity  / Current Draw | Hours  |
| ------------------------------------ | :----------------------: | :----: |
| Cell Capacity, CR2032                |    240mAh (at 200µA)     |        |
| Cap Touch Board                      |        3µA (max)         | 80,000 |
| Cap Touch Board & SS Relay (3V nom.) |          10.7mA          |  22.4  |

## Battery Options

A JST XH socket has been added to provide the option of using an alternate battery pack. Because the voltages vary different values for R1 may be necessary.

| Batteries Used                             | Max/Nom/Min Voltages |
| ------------------------------------------ | :------------------: |
| 1 x CR2032                                 |   3.4 / 3.0 / 2.7    |
| 2 x NiCd or NMH (recharable) AA or AAA     |   3.0 / 2.4 / 2.3    |
| 2 x Alkaline AA or AAA                     |    3.3 / 3.0 / ?     |
| 3 x NiCd or NMH (recharable) AA or AAA     |   4.5 / 3.6 / 3.45   |
| 3 x Alkaline AA or AAA                     |    4.95 / 4.5 / ?    |
| 1 x Li-ion (e.g. 18650) or LiPo pouch cell |   4.2 / 3.7 / 2.5    |
| 1 x LiFePO4 (LFP) cell                     |   3.65 / 3.2 / 2.0   |

**Do not use 2 x CR2016 cells** in the button cell holder as that exceeds the maximum voltage of the touch sensor.

