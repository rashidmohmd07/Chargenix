# ⚡ ChargeNix — Dynamic Wireless EV Charging System

> A hardware prototype that enables electric vehicles to charge wirelessly **while in motion** using road-embedded coils and resonant inductive coupling — eliminating range anxiety and charging stops entirely.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-Prototype-green.svg)
![Domain](https://img.shields.io/badge/domain-EV%20%7C%20Wireless%20Power-orange.svg)

---

## 📌 Table of Contents

- [About the Project](#about-the-project)
- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [How It Works](#how-it-works)
- [Block Diagram](#block-diagram)
- [Components Used](#components-used)
- [System Operation](#system-operation)
- [Results](#results)
- [SDG Mapping](#sdg-mapping)
- [Team](#team)
- [License](#license)

---

## 📖 About the Project

**ChargeNix** is a Dynamic Wireless Charging (DWC) system designed to address one of the biggest challenges in EV adoption — range anxiety and charging downtime. The system uses road-embedded transmitter coils powered by a solar panel to wirelessly transfer energy to a receiver coil mounted on the vehicle using **resonant inductive coupling**, allowing the EV to charge its battery continuously while moving.

---

## ❗ Problem Statement

Current electric vehicles face three major challenges:
- **Range anxiety** — fear of running out of battery
- **Charging delays** — time lost at fixed charging stations
- **Large battery sizes** — adding weight and cost to EVs

ChargeNix solves all three by enabling continuous wireless charging on the go.

---

## 🎯 Objectives

1. **System Design & Prototype** — Develop a high-efficiency dynamic wireless charging system for moving EVs
2. **Wireless Transfer Telemetry** — Real-time monitoring of charging performance, voltage behavior, and temperature
3. **Infrastructure Optimization** — Minimize dependence on fixed charging stations through continuous energy replenishment

---

## ⚙️ How It Works

ChargeNix uses **resonant inductive coupling** to transfer power wirelessly:

1. A **solar panel (PV array)** charges a path battery through a charge controller
2. The battery powers an **oscillator** that drives the resonant circuit
3. Road-embedded **transmitter (TX) coils** generate an alternating magnetic field
4. The EV's **receiver (RX) coil** picks up the magnetic field while moving
5. A **rectifier and filter capacitor** convert the AC to smooth DC
6. The DC charges the **EV's lithium-ion battery** via a TP-5100 charge controller
7. A **seven-segment display** shows real-time coupling status and battery voltage

---

## 🔷 Block Diagram

```
                        TRANSMITTER SIDE
┌──────────┐    ┌──────────────┐    ┌──────────┐    ┌───────────┐    ┌───────────┐    ┌──────────┐
│ PV Array │───▶│Charge Control│───▶│8.4V Batt │───▶│ Oscillator│───▶│  Resonant │───▶│ TX Coils │
└──────────┘    └──────────────┘    └──────────┘    └───────────┘    │  Circuit  │    └────┬─────┘
                                                                      └───────────┘         │
                        DYNAMIC RECEIVER SIDE                                               │
┌──────────┐    ┌──────────────┐    ┌──────────┐    ┌───────────┐    ┌──────────┐          │
│Battery(EV)│◀──│Charge Control│◀──│Filter Cap │◀──│ Rectifier │◀──│  RX Coil  │◀─────────┘
└──────────┘    └──────────────┘    └──────────┘    └───────────┘    └──────────┘
```

---

## 🔩 Components Used

### Transmitter Side
| Component | Description |
|---|---|
| PV Array (Solar Panel) | Powers the transmitter infrastructure |
| LM2596 Buck Converter | Regulates battery output voltage |
| XKT-412 Module | Converts DC to high-frequency AC for wireless transmission |
| Transmitter Coils (TX) | Road-embedded coils that generate alternating magnetic field |
| 8.4V Battery (2x 3.7V in series) | Powers the transmitter circuit |

### Receiver Side
| Component | Description |
|---|---|
| Receiver Coil (RX) | Mounted on EV, picks up magnetic field from TX coils |
| XKT-3169 Module | Converts received AC back to DC |
| Rectifier | Converts high-frequency AC to DC |
| Filter Capacitor | Smooths the rectified DC output |
| TP-5100 Charge Controller | Safely charges the lithium-ion battery |
| 5V Relay | Manually controls the charging process (ON/OFF) |
| Seven-Segment Display | Shows coupling status, voltage, and charging state |

---

## 🔬 System Operation

### Transmitter Side
- Two 3.7V batteries connected in series power the transmitter
- Output is regulated by an **LM2596 buck converter**
- Regulated DC is fed to the **XKT-412 wireless power transmitter module**, converting DC into high-frequency AC
- AC is supplied to the transmitter coil, generating an alternating magnetic field
- A **solar panel system** is integrated to sustainably charge the path battery

### Receiver Side
- Receiver coil picks up power from the alternating magnetic field
- **XKT-3169 module** converts the received signal into DC
- DC output goes through the **TP-5100 charge controller** to charge the lithium-ion battery
- A **5V relay** enables manual ON/OFF control of the charging process
- The **seven-segment display** shows:
  - Coupling status between TX and RX coils
  - Received voltage (when battery is not connected)
  - Battery charging voltage (when battery is connected)

---

## 📊 Results

A working prototype was successfully built and tested, demonstrating:
- ✅ Wireless power transfer between road-embedded TX coils and moving RX coil
- ✅ Successful lithium-ion battery charging while in motion
- ✅ Real-time voltage and coupling status display
- ✅ Solar panel integration for sustainable power input

### Prototype
> A physical prototype was constructed with a miniature EV model moving over a track with 4 embedded transmitter coils, demonstrating live wireless charging.

---

## 🌍 SDG Mapping

ChargeNix contributes to the following UN Sustainable Development Goals:

| SDG | Goal |
|---|---|
| **SDG 7** | Affordable and Clean Energy |
| **SDG 9** | Industry, Innovation and Infrastructure |
| **SDG 11** | Sustainable Cities and Communities |
| **SDG 13** | Climate Action |

---

## 👥 Team

| Name | Roll Number |
|---|---|
| Sanal Rajan | LFIT22EE064 |
| Aswin Vijay | LFIT22EE062 |
| Muhammed Rashid | LFIT22EE063 |
| Vinu P A | LFIT22EE066 |

**Project Guide:** Mr. Febin Raju

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

```
Copyright (c) 2026 Sanal Rajan, Aswin Vijay, Muhammed Rashid, Vinu P A
```

---

> *ChargeNix — Charge on the move. Power the future.* ⚡
