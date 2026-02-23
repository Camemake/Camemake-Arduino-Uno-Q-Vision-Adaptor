# Camemake-Arduino-Uno-Q-Vision-Adaptor
Open Hardware Vision Adaptor for Arduino UNO Q

[![Open Hardware](https://img.shields.io/badge/Open%20Hardware-Arduino%20Camera%20Shield-brightgreen.svg)](#)
[![Arduino UNO Q](https://img.shields.io/badge/Platform-Arduino%20UNO%20Q-blue.svg)](#)
[![MIPI CSI](https://img.shields.io/badge/Camera-MIPI%20CSI%2022--pin%20RPI5%20pinout-orange.svg)](#)
[![Dual Camera](https://img.shields.io/badge/Cameras-Dual%20MIPI%20CSI%20inputs-yellow.svg)](#)
[![RPI5 Compatible](https://img.shields.io/badge/Pinout-Raspberry%20Pi%205%20compatible-red.svg)](#)

Open hardware camera shield for Arduino UNO Q. Fits directly on the Arduino UNO Q headers. Connects two MIPI CSI cameras using the same 22-pin pinout as the Raspberry Pi 5. All Raspberry Pi 5 camera modules work on these connectors. Camemake also produces a wide range of compatible camera modules available at [camemake.eu](https://www.camemake.eu). Full design files public. Production modules sold.

[Live 3D hardware view](https://www.camemaker.com/cm-arduino-uno-v0-open-hardware-vision-adaptor-for-arduino-uno)

## What this is

CM_Arduino_UNO_V0 is an open hardware vision shield that stacks on the Arduino UNO Q and adds dual MIPI CSI camera inputs, using the identical 22-pin FPC connector pinout as the Raspberry Pi 5.

This means every Raspberry Pi 5 compatible camera module plugs straight in — no rewiring, no adaptor, no pinout translation. Camemake also offers a growing range of camera modules designed for this exact connector at [camemake.eu](https://www.camemake.eu).

The shield exposes:
- Two 22-pin MIPI CSI camera connectors, pinout identical to Raspberry Pi 5
- Full compatibility with the Raspberry Pi camera module ecosystem
- Camemake camera module compatibility across development kits
- Direct plug-in fit on Arduino UNO Q standard headers
- Full schematic, PCB, BOM, mechanical, and firmware data published

This platform is meant for:
- Vision and imaging add-ons for Arduino UNO Q based systems
- Dual camera setups for stereo vision, multi-angle capture, or redundancy
- Rapid prototyping using the broad RPI5 camera module ecosystem
- Students, makers, and engineers who want camera vision on Arduino UNO Q

---

## 1. Key points

- Open hardware shield: CM_Arduino_UNO_V0
- Host platform: Arduino UNO Q
- Camera connectors: 2× 22-pin FPC, pinout identical to Raspberry Pi 5 CSI camera connector
- Camera compatibility: All Raspberry Pi 5 camera modules, all Camemake RPI-pinout modules
- Connector standard: 22-pin, same physical and electrical pinout as RPI5 camera port
- Stacking: Direct fit on Arduino UNO Q standard shield headers
- Full CAD, firmware reference, and manufacturing data provided

This shield is both:
1. A reference design you can copy and adapt.
2. A production-ready add-on you can buy assembled.

---

## 2. Block diagram (functional roles)

**Arduino UNO Q (host)**
- Host controller providing power, I2C control bus, and data interface to the shield
- Standard Arduino UNO shield header footprint

**CM_Arduino_UNO_V0 shield (this board)**
- Dual 22-pin FPC MIPI CSI camera connectors
- Pinout electrically and mechanically identical to Raspberry Pi 5 camera port
- Camera power rails: 1.8 V and 2.8 V image sensor supply domains
- I2C / TWI control lines for sensor init and register access
- Camera enable, reset, and power sequencing per port
- Shield headers passing through UNO Q pins

**Camera modules (plug-in, not included)**
- Any Raspberry Pi 5 compatible camera module (22-pin FPC)
- Any Camemake camera module with RPI5-compatible 22-pin pinout
- Available at [camemake.eu](https://www.camemake.eu)

---

## 3. Camera connector and ecosystem

The CM_Arduino_UNO_V0 shield is camera-first.

- Both camera connectors use the same 22-pin pinout as the Raspberry Pi 5 CSI camera port
- This is a fixed, documented pinout — identical signal assignment, identical FPC pitch
- This means:
  - Every RPI5 camera module plugs straight in
  - All Camemake RPI-pinout camera modules work without modification
  - Camera firmware, I2C drivers, and init sequences developed for RPI5 ecosystem are directly reusable

Connector specification:
- 22-pin FPC flat flex connector
- Pinout: identical to Raspberry Pi 5 camera CSI port
- 2 independent ports on a single shield
- Supported sensor interfaces: MIPI CSI-2 (as supported by connected host and sensor)

Power rails per camera port:
- 1.8 V core / IO supply for image sensor
- 2.8 V analog supply for image sensor
- Enable and sequencing control per port

Camera modules compatible with this shield:
- Any third-party RPI5 22-pin CSI camera module
- Camemake RPI camera modules (see [camemake.eu](https://www.camemake.eu))

---

## 4. Networking and I/O

### Host interface
- Shield plugs into Arduino UNO Q standard headers
- I2C bus used for camera sensor control (address-selectable per port)
- GPIO lines for camera reset, enable, and power sequencing
- SPI or UART available via pass-through headers depending on firmware configuration

### Storage and expansion
- Expansion header pass-through for stacking with other shields
- No onboard storage; host Arduino UNO Q manages data flow

---

## 5. Hardware deliverables in this repo

You get full manufacturing data.

- Schematics (PDF and source)
- PCB layout files
- IPC-class PCB stackup and impedance spec
- BOM with part numbers
- Mechanical files (STEP, DXF)
- Pinout drawings for:
  - 22-pin camera connector A (RPI5-identical)
  - 22-pin camera connector B (RPI5-identical)
  - Arduino UNO Q shield header mapping
  - Power rail tree
- Power sequencing notes
- Reflow and assembly guidance

This is meant to let you build your own carrier or integrate this into a product, not just test a sensor.

---

## 6. Live hardware view (3D board)

A live, interactive 3D view of the CM_Arduino_UNO_V0 shield is available here:

https://www.camemaker.com/cm-arduino-uno-v0-open-hardware-vision-adaptor-for-arduino-uno

The page below embeds the Altium 365 viewer so you can inspect the full assembly, component placement, and mechanical envelope in the browser:

<iframe src="https://personal-viewer.365.altium.com/client/index.html?feature=embed&source=19813A17-C337-4DAA-BEE3-FFF654861E34&activeView=PCB" width="1280" height="720" style="overflow:hidden;border:none;width:100%;height:720px;" scrolling="no" allowfullscreen="true" onload="window.top.scrollTo(0,0);"></iframe>

---

## 7. Camera modules

Camemake produces a range of camera modules compatible with this shield's 22-pin RPI5-pinout connectors.

Browse available modules at: [https://www.camemake.eu](https://www.camemake.eu)

These include sensors for:
- Standard FOV imaging
- Wide angle and fisheye
- High resolution stills
- Industrial and machine vision use cases

All modules use the same physical connector and pinout as the Raspberry Pi 5, so they fit both this shield and RPI5-based systems interchangeably.
