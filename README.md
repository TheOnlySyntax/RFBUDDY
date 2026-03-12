# RF Buddy 0.2v — Web Flasher & Info

**RF Buddy** is a compact, closed-source ESP32-C3 based sub-GHz radio tool designed for security researchers and electronics enthusiasts.  
This repository hosts the official [GitHub Pages site](https://theonlysyntax.github.io/RF-BUDDY/) with device specifications and the **web-based firmware flasher**.

🔗 **Live site:** [https://theonlysyntax.github.io/RF-BUDDY/](https://theonlysyntax.github.io/RF-BUDDY/)

---

## ℹ️ About This Repository

This repo **does not contain the device firmware source code**.  
It only contains the static website used for:

- 📋 **Device information** (hardware specs, pinout, features)
- ⚡ **Web flasher utility** — flash firmware directly from your browser using Web Serial API

The firmware itself is **closed source** and distributed separately via pre-compiled `.bin` files.

---

## Hardware Overview

| Component | Detail |
|-----------|--------|
| MCU | ESP32-C3 |
| Radio | CC1101 |
| Display | SSD1306 128×64 OLED (I²C) |
| Buttons | UP · DOWN · OK · BACK |
| Storage | 4 MB SPIFFS (internal flash) |

### Pin Map

| Signal | GPIO |
|--------|------|
| CC1101 CS | 7 |
| CC1101 MOSI | 6 |
| CC1101 MISO | 5 |
| CC1101 SCK | 4 |
| CC1101 GDO0 | 20 |
| OLED SDA | 8 |
| OLED SCL | 9 |
| BTN UP | 0 |
| BTN DOWN | 1 |
| BTN OK | 3 |
| BTN BACK | 10 |

---

## Firmware Features

The device runs a closed-source firmware with the following capabilities:

### Menu Structure
Carousel of 5 cards: **FS · BLE · RX · TX · SET**

### RX Modes
- **Read Signal** — protocol decoding + TX replay (Princeton, CAME, Nice FLO, KeeLoq, Holtek, Hörmann, Doorhan, StarLine, FAAC, Ansonic, Linear, BFT, DEA, Sommer, Gibidi, Aprimatic, Elmes, Pixxo, Clevo, Generic RAW)
- **Read RAW** — raw waveform capture + replay
- **Analyzer** — RSSI peak finder with history
- **Spectrum** — bargraph per frequency band
- **Waterfall** — rolling RSSI heatmap

### TX Modes
- **Jammer** — pulse / noise / carrier / sweep
- **Bruteforce** — sequential code brute-forcer (Princeton, CAME, Nice FLO, Holtek, Chamberlain, Liftmaster, Ansonic, Linear, SMC5326)
- **Saved** — play back `.sub` files from SPIFFS

### File Format
Signals are saved as Flipper Zero compatible `.sub` files (RAW format).

---

## Web Flasher

The site includes a **browser-based flashing tool** powered by the Web Serial API:

1. Connect your RF Buddy via USB
2. Click "Connect Device" in Chrome/Edge/Opera
3. Select a firmware `.bin` file
4. Click "Flash Firmware"

The flasher handles:
- Automatic bootloader entry (DTR/RTS toggling)
- Flash erase
- Firmware write with progress bar
- Verification and device reset
---

## Disclaimer & Legal

**RF Buddy is a closed-source tool intended for educational and authorized research purposes only.**

- ⚠️ **RF jamming is illegal in most jurisdictions.**
- 🚫 The firmware source code is **not publicly available**.
- 📡 Always check local regulations before transmitting on any frequency.
- The maintainers are **not responsible for any misuse** of this device.

For firmware updates, pre-compiled `.bin` files are distributed separately.
