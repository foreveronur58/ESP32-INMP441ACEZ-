# HONUR.SOLO Mic Board

A custom 2-layer PCB built around the ESP32-S3-MINI-1 module, with an INMP441
I2S MEMS microphone, powered over USB-B. Designed in KiCad.

## Features
- ESP32-S3-MINI-1-N8 (WiFi + BLE + native USB)
- INMP441 I2S digital microphone
- AMS1117-3.3 regulator (5V VBUS -> 3.3V)
- Mini USB-B connector
- EN and BOOT buttons, status LED
- Board size: XX x XX mm, 2 layers, 1.6 mm

## Repository Contents
- `*.kicad_sch`, `*.kicad_pcb`: schematic and PCB layout
- `gerber/`: fabrication files (JLCPCB)
- `bom/`: BOM and CPL files for PCBA
- `docs/`: datasheet links and render images

## Design Notes
- GND copper pour on B.Cu; the ESP32 thermal pad is stitched to it with vias
- No copper or vias under the ESP32 antenna area (keepout respected)
- All footprints were checked against manufacturer land patterns
- The INMP441 footprint from SnapMagic had an acoustic port hole of
  0.75 mm instead of the 0.25 mm in the datasheet, which caused a hole
  clearance DRC violation. Fixed by correcting the hole diameter
  (0.3 mm to stay within JLCPCB's minimum drill size).
- Net classes configured for JLCPCB's standard 2-layer capabilities

## Status
- [x] Schematic
- [x] PCB placement and routing
- [x] DRC clean
- [ ] Fabrication (JLCPCB PCBA)
- [ ] Hardware bring-up and testing

## License
All rights reserved.
