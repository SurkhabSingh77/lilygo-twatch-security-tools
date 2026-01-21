# LilyGO T-Watch S3 — Educational & Ethical WiFi Security Toolkit

Version: 1.0.0  
Last updated: 2026-01-21

Short description
- Educational toolkit for secure, lab-only WiFi security experiments and detection prototyping on the LilyGO T-Watch S3 (ESP32-S3).

Overview
- This repository provides firmware examples, host-side utilities, and documentation for safe, ethical WiFi security research using the LilyGO T-Watch S3 (ESP32-S3). It is intentionally focused on teaching, reproducibility, and defensive techniques: passive logging, telemetry, isolated experiment scenarios, and lightweight detection proofs-of-concept suitable for constrained devices.

Ethics & legal disclaimer (read first)
- All experiments MUST be performed only on devices and networks you own or where you have explicit, documented permission.
- Intercepting, interfering with, or attacking networks or devices you do not own or are not authorized to test is illegal and unethical.
- Use this project only for education, defensive research, and authorized testing. If you discover third-party vulnerabilities, follow responsible disclosure procedures and vendor guidance.

Supported hardware
- LilyGO T-Watch S3 (ESP32-S3) — other ESP32-S3 boards may be compatible with small changes
- Recommended: a separate WiFi adapter for host-side monitor-mode captures (Linux recommended)

Tools & software
- ESP-IDF (recommended for low-level features)
- PlatformIO or Arduino-ESP32 (easier/high-level alternative)
- esptool.py (flashing)
- Python 3.8+ (host scripts)
- Wireshark / tcpdump (packet analysis)
- scapy (crafted-frame experiments on host; only in lab)
- hostapd / dnsmasq (isolated APs)
- Recommended: Git, make, and a serial terminal (minicom / picocom / idf.py monitor)

Repository layout (recommended)
- firmware/
  - espidf/               — ESP-IDF projects and build instructions
  - platformio/           — PlatformIO projects and convenience sketches
  - arduino/              — Arduino sketches (if provided)
- tools/
  - capture/              — host capture helpers (pcap rotate, metadata extract)
  - analysis/             — small Python analysis scripts (RSSI histograms, CSV exporters)
  - deploy/               — flashing helpers and serial-log collectors
- docs/
  - design/               — architecture, diagrams, and testbed design notes
  - experiments/          — step-by-step lab scenarios and expected outcomes
  - ethics.md             — detailed ethical guidance & responsible disclosure checklist
- examples/
  - passive-logger/       — safe, anonymized metadata logger (rate-limited)
  - beacon-lab/           — controlled beacon/probe generation (isolated networks only)
  - anomaly-detector/     — lightweight detection prototype (on-device)
- tests/
  - ci/                   — small host-unit tests and linters
  - hw/                   — hardware test procedures and checklists
- .github/
  - ISSUE_TEMPLATE.md
  - PULL_REQUEST_TEMPLATE.md
- requirements.txt        — Python dependencies for host tools
- LICENSE
- README.md

Example folder-tree (visual)
- /
  - firmware/
  - tools/
  - docs/
  - examples/
  - tests/
  - .github/
  - requirements.txt
  - LICENSE
  - README.md

Quickstart (safe lab steps)
1. Prepare an isolated lab environment
   - Create an isolated WiFi SSID or VLAN with no production devices and no internet access.
   - Use a separate host WiFi adapter in monitor mode for passive capture when needed.
   - Ensure you have permission for any equipment you test.

2. Prerequisites (host)
   - Install Python 3.8+ and pip: pip install -r requirements.txt
   - Install ESP-IDF or PlatformIO per official docs.
   - Install Wireshark for traffic analysis.

3. Build and flash (PlatformIO example)
   - Open the PlatformIO project in `firmware/platformio/`
   - Select the T-Watch S3 board, connect USB, and run Upload
   - Or use: pio run -e <env> -t upload

4. Build and flash (ESP-IDF example)
   - cd firmware/espidf/<project>
   - idf.py set-target esp32s3
   - idf.py build
   - idf.py -p <PORT> flash monitor

5. Monitor & capture
   - Use idf.py monitor or a serial terminal to observe device logs.
   - For packet capture use a dedicated monitor interface and Wireshark (only in lab).
   - Use the provided tools in `tools/capture/` to rotate pcaps and export anonymized metadata.

Safe example experiments (only in controlled lab)
- Passive metadata logging: collect anonymized frame metadata (timestamp, frame type, RSSI) and avoid storing MACs or payloads unless necessary — and then immediately anonymize/secure them.
- Beacon/probe simulation: generate a small, rate-limited set of beacons on an isolated AP to test detection signatures.
- On-device anomaly detection: run a tiny ML rule or heuristics to flag management frame anomalies and report only aggregated alerts.

Security & privacy best practices
- Avoid capturing or storing plaintext payloads or personally identifiable information (PII).
- Encrypt any telemetry sent off-device and restrict access to stored captures.
- Delete or securely store experimental captures once analysis is complete.

Learning outcomes
- Familiarity with LilyGO T-Watch S3 hardware and ESP32-S3 toolchains.
- Practical understanding of 802.11 management frames and WiFi telemetry sources.
- How to build reproducible, isolated wireless testbeds.
- How to implement simple on-device detection and responsibly handle captured data.
- Ethical research practices including permission models and responsible disclosure.

Contributing (ethical-first)
- Contributions are welcome but must preserve the educational and ethical focus.
- Open an issue to discuss potentially sensitive experiments before submitting PRs.
- Mark any code that could be misused with clear warnings and safe defaults (rate-limits, disabled-by-default dangerous examples).
- Follow the contributor guidelines in .github/ and sign any required DCO if present.

Responsible disclosure & reporting
- If you discover a vulnerability in third-party products, stop active testing, collect minimal PoC data, and follow the vendor's vulnerability disclosure process.
- If no vendor process exists, contact the vendor privately and allow reasonable time for remediation.
- Document your actions and retain proof of permission for your experiments.

Testing & CI
- Keep CI focused on linters and host-side tests; do not automate hardware attacks.
- Use unit tests for parsing/analyzing scripts in `tools/analysis/`.
- Manual hardware-in-the-loop checks belong in `tests/hw/` and must be documented.

License
- Choose an appropriate open-source license (e.g., MIT or Apache-2.0). Include a LICENSE file.

Contact & support
- File issues on GitHub or contact the repo owner. For this template, replace with your GitHub handle or project maintainer contact.

Acknowledgements
- This project is intended for teaching and defensive research. Always secure explicit authorization before running experiments on third-party equipment or networks.

