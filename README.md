<div align="center">

  <img src="Images/Headless_Nick_Banner.PNG" alt="Headless Nick Banner" width="100%"/>

  <br/>
  <br/>

  <p align="center">
    <a href="https://github.com/GH0ST3CH/Headless_Nick"><img src="https://img.shields.io/static/v1?label=GH0ST3CH%20X%20REDHAT&message=Headless%20Nick&color=7e57c2&logo=github" alt="GH0ST3CH X REDHAT Headless Nick"/></a>
    <img src="https://img.shields.io/badge/GhostESP-Compatible-7e57c2" alt="GhostESP Compatible"/>
    <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-7e57c2" alt="MIT license"/></a>
  </p>

  <p align="center">
    <a href="https://www.instagram.com/cyb3rb3ast"><img src="https://img.shields.io/static/v1?label=GH0ST3CH&message=Instagram&color=7e57c2&logo=instagram&logoColor=white&logoPosition=right" alt="GH0ST3CH on Instagram"/></a>
    <a href="https://www.instagram.com/redihat_labs"><img src="https://img.shields.io/static/v1?label=REDHAT&message=Instagram&color=7e57c2&logo=instagram&logoColor=white&logoPosition=right" alt="REDHAT on Instagram"/></a>
    <a href="https://www.tiktok.com/@gh0st3chr3pair"><img src="https://img.shields.io/static/v1?label=GH0ST3CH&message=TikTok&color=7e57c2&logo=tiktok&logoColor=white&logoPosition=right" alt="GH0ST3CH on TikTok"/></a>
    <a href="https://youtube.com/@GhosTechRepair"><img src="https://img.shields.io/static/v1?label=GH0ST3CH&message=YouTube&color=7e57c2&logo=youtube&logoColor=white&logoPosition=right" alt="GH0ST3CH on YouTube"/></a>
    <a href="https://discord.gg/apukq2VZxd"><img src="https://img.shields.io/static/v1?label=GH0ST3CH&message=Discord&color=7e57c2&logo=discord&logoColor=white&logoPosition=right" alt="GH0ST3CH on Discord"/></a>
  </p>

  <p align="center">
    <a href="https://github.com/GH0ST3CH/Headless_Nick"><img src="https://img.shields.io/github/stars/GH0ST3CH/Headless_Nick?style=social" alt="GitHub stars"/></a>
    <a href="https://github.com/GH0ST3CH/Headless_Nick"><img src="https://img.shields.io/github/forks/GH0ST3CH/Headless_Nick?style=social" alt="GitHub forks"/></a>
  </p>

</div>

<div>&nbsp;</div>

## :star2: About the Project

**Headless Nick** is a custom hardware build made to work with **GhostESP firmware** and its **GhostLink** feature. It brings together two Seeed Studio XIAO ESP32-C5 boards, a MicroSD card tray, and a rechargeable 18650 battery on a custom PCB.

The MicroSD tray connects to the Main XIAO. The two XIAO boards communicate over crossed GPIO connections, while a TP4056 charging module is wired to the battery pads on both boards. A physical switch lets the device be powered off while the battery charges.

> ⚠️ Headless Nick is an independent hardware project. It is designed for use with GhostESP, but it is **not made by or affiliated with the GhostESP project**.

<img width="100%" alt="Headless Nick device" src="Images/Headless_Nick.PNG" />

<div>&nbsp;</div>

## ✨ Highlights

- ⚙ **Dual XIAO ESP32-C5 boards** – two boards connected for GhostLink use
- 🔗 **Cross-connected GPIO** – Main GPIO 23 connects to second GPIO 24, and Main GPIO 24 connects to second GPIO 23
- 💾 **MicroSD card tray** – wired to the Main XIAO only
- 🔋 **18650 battery power** – rechargeable battery-based build
- 🔌 **TP4056 charging** – charger connected to the battery pads on both XIAO boards
- 🎚 **Power switch** – switch the device off while charging
- 🧩 **Custom PCB** – combines the boards, card tray, charging module, and power connections
- 👻 **GhostESP compatible** – configure GhostLink TX to 23 and RX to 24 after flashing both boards

<div>&nbsp;</div>

## 🔌 Hardware Overview

### Core

- **Main board:** Seeed Studio XIAO ESP32-C5
- **Second board:** Seeed Studio XIAO ESP32-C5
- **Storage:** MicroSD card tray connected to the Main XIAO
- **Inter-board link:** GPIO 23 and GPIO 24 cross-connected between the boards

### Power

- **Battery:** 18650 rechargeable cell
- **Charger:** TP4056
- **Charging connection:** TP4056 wired to the battery pads on both XIAO ESP32-C5 boards
- **Power control:** physical switch for turning the device off while charging

<div>&nbsp;</div>

## 🧷 Wiring

### MicroSD card tray → Main XIAO ESP32-C5

The MicroSD tray is connected to the **Main XIAO only**. It is not connected to the second XIAO.

| MicroSD card tray | Main XIAO ESP32-C5 |
|-------------------|--------------------|
| CS                | D0                 |
| CLK               | D8                 |
| MOSI              | D10                |
| MISO              | D9                 |
| VCC               | 3V3                |
| GND               | GND                |

### Main XIAO ESP32-C5 ↔ Second XIAO ESP32-C5

| Main XIAO ESP32-C5 | Second XIAO ESP32-C5 |
|--------------------|----------------------|
| GPIO 23 (D4)       | GPIO 24 (D5)         |
| GPIO 24 (D5)       | GPIO 23 (D4)         |

### Battery and charging

The TP4056 is wired to the battery pads on both XIAO ESP32-C5 boards. Check polarity and inspect the wiring before connecting the battery or powering the device.

## 🧰 GhostESP / GhostLink Setup

1. Flash GhostESP firmware to **both** XIAO ESP32-C5 boards.
2. Configure GhostLink with **TX = 23** and **RX = 24**.
3. Keep the MicroSD card tray connected to the Main XIAO only.

The GhostLink TX/RX settings use GPIO numbers. The physical board-to-board wiring is crossed: Main GPIO 23 goes to second GPIO 24, and Main GPIO 24 goes to second GPIO 23.

<div>&nbsp;</div>

## 🤓 DIY

You can DIY Headless Nick by following this schematic:

<img width="100%" alt="Headless Nick DIY schematic and wiring reference" src="Images/Headless_Nick_DIY_Sch.png" />

<div>&nbsp;</div>


## 🙌 Shoutout / Acknowledgments

**Big** shoutout to **REDHAT** (Surya Rapeti) for re-sizing the PCB (made it smaller), adding resistors and the capacitor necessary for the MicroSD card tray to work right and troubleshooting the PCB design software that was used to create Headless Nick.

**Big** shoutout to **DUGGIE TECH** for initiating and mentoring me through the process of designing the 3D printed case for Headless Nick.

**HUGE** shoutout to the [**GhostESP: Revival**](https://github.com/GhostESP-Revival/GhostESP) project for being the spirit that I designed Headless Nick to possess 👻


## :warning: License

Distributed under the MIT License. See [LICENSE](LICENSE) for more information.

## :handshake: Contact

Find me on [Instagram](https://www.instagram.com/cyb3rb3ast), [TikTok](https://www.tiktok.com/@gh0st3chr3pair), [YouTube](https://youtube.com/@GhosTechRepair) and [Discord](https://discord.gg/apukq2VZxd).
