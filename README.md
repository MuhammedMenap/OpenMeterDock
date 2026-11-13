# OpenMeterDock

**Open-source ESP32-based utility meter monitoring with Home Assistant integration and modular 3D-printable sensor mounts.**

![Status](https://img.shields.io/badge/status-planning-yellow)
![License](https://img.shields.io/badge/license-Apache--2.0-blue)
![Platform](https://img.shields.io/badge/platform-ESP32-green)
![Home Assistant](https://img.shields.io/badge/integration-Home%20Assistant-blue)

> **Project status:** Early development. The architecture and initial scope are being defined. No tested firmware or production-ready hardware has been released.

## Overview

OpenMeterDock aims to make existing utility meters smarter without requiring expensive replacements or modifications to their internal components.

The project focuses on affordable, non-invasive monitoring of gas, water, and electricity consumption using ESP32 microcontrollers, compatible external sensors, and modular 3D-printable mounting systems.

Our goal is to make utility consumption data accessible through Home Assistant while keeping the platform transparent, repairable, and open source.

## Project Goals

- Affordable, locally controlled utility monitoring
- Compatibility with multiple meter types and sensor technologies
- Non-invasive installation wherever technically possible
- ESP32-based data acquisition and processing
- Home Assistant integration
- Modular and customizable 3D-printable sensor mounts
- Documented calibration and validation procedures
- Community-driven hardware and software development

## Planned Architecture

```text
Gas Meter    ---- [Compatible Pulse / Magnetic Sensor] ---+
Water Meter  ---- [Compatible Pulse / Optical Sensor] ----+--> ESP32
Electricity  ---- [Isolated Pulse Sensor / Interface] ----+
                                                             |
                                                      Wi-Fi / Local Network
                                                             |
                                                       Home Assistant
                                                             |
                                                Dashboards / History / Alerts
```

Sensor compatibility depends on the meter model. Not every meter exposes a readable pulse output or supports an external magnetic or optical sensor.

## Technology Stack

| Component | Initial Direction |
|---|---|
| Microcontroller | ESP32 |
| Firmware | ESPHome-based prototype |
| Smart home platform | Home Assistant |
| Connectivity | Wi-Fi |
| Sensor interfaces | Pulse, magnetic, optical (subject to validation) |
| Mechanical design | Parametric 3D-printable mounts |
| Enclosure manufacturing | FDM 3D printing |
| Licensing | Apache License 2.0 |

## Development Roadmap

### Phase 1 — Gas Meter Prototype
- [ ] Select and document the first compatible gas meter
- [ ] Evaluate non-invasive pulse sensing methods
- [ ] Build an ESP32-based proof of concept
- [ ] Implement pulse counting and configurable meter calibration
- [ ] Publish initial firmware and wiring documentation
- [ ] Verify readings against the physical meter

### Phase 2 — Home Assistant Integration
- [ ] Expose meter readings through ESPHome
- [ ] Track cumulative consumption
- [ ] Implement persistence and restart recovery
- [ ] Create a sample Home Assistant dashboard
- [ ] Document installation and troubleshooting

### Phase 3 — Mechanical Design
- [ ] Design a modular sensor mounting system
- [ ] Publish 3D-printable models and source CAD files
- [ ] Test fit, stability, and repeatable sensor alignment
- [ ] Document installation for supported meter models

### Phase 4 — Extended Compatibility
- [ ] Investigate water meter support
- [ ] Investigate isolated electricity meter pulse interfaces
- [ ] Add configurable calibration profiles
- [ ] Publish measurement accuracy and reliability test results
- [ ] Invite community contributions and hardware feedback

## Measurement and Reliability

OpenMeterDock is intended for supplemental monitoring, not certified utility billing.

The project will investigate:

- Missed or duplicate pulse detection
- Input filtering and debounce
- Counter persistence across power loss
- Sensor alignment and interference
- Calibration uncertainty and long-term repeatability
- Recovery after Wi-Fi or Home Assistant disconnection

Accuracy specifications will be published only after testing.

## Safety

This project does not require opening, modifying, bypassing, or interfering with utility meters or their seals.

Only appropriate external sensing methods and electrically isolated interfaces should be used. Utility provider requirements and local electrical safety rules must be respected.

Do not connect ESP32 GPIO pins directly to mains voltage or unisolated meter circuits.

## Contributing

Contributions, technical suggestions, compatibility reports, documentation improvements, and hardware design ideas are welcome.

During the early development stage, please use GitHub Issues to discuss proposed features, meter compatibility, and implementation approaches.

Firmware, CAD files, and test results will be added progressively as development and validation proceed.

## License

Licensed under the [Apache License 2.0](LICENSE).

## Maintainer

**MuhammetHasanMenap**  
Electrical & Electronics Engineering | Embedded Systems | IoT | Hardware Prototyping

[GitHub Profile](https://github.com/MuhammedMenap)

---

**OpenMeterDock — Making utility monitoring more accessible, one meter at a time.**
