# PentoGraf-DivMMC-x2

DivMMC (Aurora clone) & DivMMC + Z-Controller with Dual ROM for PentoGraf computer.

> [English](README.en.md) | [Русский](README.md)

---

## 📋 Version Description

### 🛠 Version 1: DivMMC "Aurora Edition" (Classic)
A complete hardware clone of the classic **DivMMC by Aurora**, adapted for the PentoGraf system bus slot.
* **Core:** Original DivMMC logic.
* **Interface:** SD card slot.
* **Compatibility:** Full out-of-the-box compatibility with standard software and **esxDOS** operating system.
* **Differences from the original:** Only the form-factor and edge connector pinout were modified to fit the PentoGraf expansion slot.

[iBOM](Schematics/DivMMC_PentoGraf.html) | [Schematic](Schematics/DivMMC_PentoGraf.pdf) | [Gerber](Gerber/DivMMC_PentoGraf_Gerber.zip)

### 🚀 Version 2: Dual ROM & Z-Controller (Advanced)
An advanced modification based on the [DivMMC2ROM by Electrophysic](https://github.com) project, adapted for the PentoGraf system bus slot.
* **Dual ROM Architecture:** The board features two ROM chips. One ROM stores the standard firmware (esxDOS), while the second ROM acts as a hardware address decoder.
* **Z-Controller Support:** Along with the standard DivMMC mode, the board features integrated hardware logic for the **Z-Controller** (an SD card interface highly popular among classic post-Soviet ZX Spectrum clones like Pentagon).
* **Simultaneous Operation:** Both DivMMC and Z-Controller interfaces work in parallel and simultaneously. No manual toggling or switches are required.
* **Universal SRAM Footprint:** The PCB layout features a combined DIP/SOP footprint, allowing you to use **three different types of static RAM** seamlessly without any jumpers (auto-detected):
  1. **AS6C4008** (512 KB, DIP-32 package)
  2. **IS61C1024** (128 KB, DIP-32 package)
  3. **K6X4008** (512 KB, SOP-32 package)
* **Versatility:** The perfect choice for developers and enthusiasts seeking maximum compatibility with various modern and legacy software.

[iBOM](Schematics/DivMMC_2ROM_discreet.html) | [Schematic](Schematics/DivMMC_2ROM_discreet.pdf) | [Gerber](Gerber/DivMMC_2ROM_discreet_Gerber.zip)

---

## 🛠 Technical Details

* **System Slot:** Custom pitch and pinout designed specifically for the **PentoGraf** expansion slot.
* **Power Supply:** +5V supplied from the system bus.
* **Supported OS/Software:** esxDOS (for both DivMMC modes), Fatall / Wild Commander (WOS) (for Z-Controller mode).

---

## 🚀 Quick Start

1. **Manufacturing:** Go to the desired version folder, download the Gerber archive, and order the boards from any PCB manufacturer (JLCPCB, PCBWay, etc.).
2. **Assembly:** Solder components according to the interactive BOM and placement sheets. No jumper configuration is needed for RAM type selection.
3. **Flashing Firmware:**
   * The **DIV ROM** image is identical for both hardware versions. Get the firmware binary [here](Firmware/ROM.bin)
   * For dual SD card support (Dual ROM mode), flash this image into the **ADR ROM**: [Download ROM](Firmware/AdrDiv.bin)
   * For the DivMMC + Z-Controller mode, flash this image into the **ADR ROM**: [Download ROM](Firmware/AdrDivZ2card.bin)
4. **SD Card Preparation:**
   * Format your SD card to **FAT32**.
   * For DivMMC functionality: Copy the official **esxDOS** system directories (`/SYS` and `/BIN`) directly to the root of the card.
5. **First Boot:** Insert the controller into the PentoGraf expansion slot while the computer is powered off. Insert the prepared SD card and power on the system.

---

## 📜 License and Acknowledgements

* This project is distributed under the open-source **MIT License**.
* Thanks to **AlexEkb** for the original and reliable discrete-logic DivMMC schematic design.
* Special thanks to **Electrophysic** for the [DivMMC2ROM](https://github.com) project, which served as the hardware core for Version 2 of this controller.

