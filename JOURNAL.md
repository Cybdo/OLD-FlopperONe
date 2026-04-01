---
title: "Flipper Zero Clone"
author: "Ryan"
description: "A custom open-source multi-tool PCB with sub-GHz RF, NFC, IR, and OLED display in a 3D printed enclosure."
created_at: "2026-03-20"
---

# March 20: Research and schematic planning

Spent the afternoon going through the official Flipper Zero schematics on GitHub to understand how the RF, NFC, and IR subsystems are wired together. Decided to use the STM32WB55 as the main MCU since it handles BLE and has enough GPIO for all the peripherals. Started a rough block diagram in KiCad to map out power rails and communication buses.

![block diagram](images/block-diagram.png)

**Total time spent: 3 hours**

# March 22: Schematic capture in KiCad

Got the full schematic roughed out. Wired up the CC1101 to the STM32 over SPI, connected the PN532 NFC module over I2C, and added the IR transmitter and receiver pair on dedicated GPIO pins. The TP4056 charger circuit was straightforward. Still need to double-check the antenna matching network for the CC1101.

![schematic](images/schematic-v1.png)

**Total time spent: 4 hours**

# March 24: PCB layout started

Moved into the PCB editor and started placing components. Kept the RF section isolated on one side of the board to reduce interference. The STM32WB55 QFN package was tricky to place decoupling caps for, had to read the datasheet recommendations carefully. Power section is mostly routed. Antenna keepout zone added.

![pcb layout](images/pcb-v1.png)

**Total time spent: 5 hours**

# March 26: Routing finished, sent to fab

Finished routing all signal lines and ran the DRC. Had a few clearance violations around the USB-C connector footprint that took a while to sort out. Exported Gerbers and placed the order through JLCPCB. Also put in a parts order on LCSC for all the SMD components. Estimated delivery is about 10 days.

![gerber preview](images/gerber-preview.png)

**Total time spent: 3 hours**

# March 28: Enclosure design in CAD

While waiting for the PCBs, started modelling the enclosure in Fusion 360. Designed around the PCB outline with cutouts for the OLED, USB-C port, and buttons. Printed a test shell in PLA to check fitment, a few tolerances were off around the display window so adjusted and queued another print overnight.

![enclosure prototype](images/enclosure-v1.jpg)

**Total time spent: 4 hours**
