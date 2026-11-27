# LilyGO T-Watch S3 — Bruce Firmware Exploration

A hands-on learning record for using the LilyGO T-Watch S3 (ESP32-S3) with the open-source Bruce firmware.

> **Status:** Documentation only at present. This repository does not contain a custom security toolkit, independently developed firmware, host-side utilities, automated tests, or a CI pipeline.

## Overview

I used a LilyGO T-Watch S3 smartwatch as a portable embedded device for learning about ESP32 hardware and wireless-security concepts. I installed Bruce firmware using the project's web flasher and explored the functionality provided by the firmware.

This repository documents my use of the hardware and upstream firmware. It does not claim that I created Bruce, implemented its features, or developed a separate Wi-Fi security toolkit.

## Hardware

- **Device:** LilyGO T-Watch S3
- **Microcontroller family:** ESP32-S3
- **Firmware used:** [Bruce](https://github.com/pr3y/Bruce)
- **Installation method:** Bruce web flasher

The exact hardware revision, firmware release, and installation date have not yet been recorded. These will be added after verification.

## What I did

- Flashed Bruce firmware onto the T-Watch S3 using the project's web flasher.
- Explored the features available in the firmware.
- Used the device for hands-on learning about wireless networking and embedded security.
- Compared the T-Watch S3 experience with other hardware in my lab, including the M5StickC Plus2 and a 2.8-inch CYD touchscreen board.

## Upstream project attribution

Bruce is an independent open-source project: [pr3y/Bruce](https://github.com/pr3y/Bruce).

The firmware, its implementation, and its built-in features belong to their respective upstream authors and contributors. This repository records my hardware use, setup experience, and learning notes. Any upstream assets or code will retain their original licensing and attribution.

## Safe and authorized use

I use security-testing features only with devices and networks I own or have explicit permission to assess. I do not publish credentials, private network identifiers, or other people's traffic. Experiments should be controlled and should not disrupt nearby networks or devices.

## Repository status and future work

This repository is currently a record of device usage rather than a source-code toolkit. Future additions may include:

- [ ] Verified device revision and hardware specifications
- [ ] Bruce release/version used
- [ ] My own installation photos and setup notes
- [ ] Notes on device controls, display, battery, and connectivity
- [ ] Safe experiment logs describing purpose, setup, observations, and limitations
- [ ] Links to relevant upstream documentation

No feature will be described as implemented by me unless I add and verify my own code for it.

## References

- [LilyGO](https://github.com/Xinyuan-LilyGO)
- [Bruce firmware](https://github.com/pr3y/Bruce)
- [Espressif ESP32-S3 documentation](https://docs.espressif.com/projects/esp-idf/en/latest/esp32s3/)

---
A practical record of learning through real hardware, careful experimentation, and accurate attribution.
