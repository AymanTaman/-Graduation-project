#  Directional Antenna Controller for UAV Data Link

> **CEN 493 – Graduation Project** | Department of Computer Engineering | 2nd Semester 2026

**Team:** Ayman Saleh Taman · Abdullah Hamad Alghuzza · Mohammed Saleh Althagafi · Abdulrahman Amin Mansour

**Advisors:** Dr. Abdulmohsen Almutairi & Dr. Salman Alqahtani

📄 [CEN493 Directional Antenna Controller for UAV Data Link](./CEN493%20Directional%20Antenna%20Controller%20for%20UAV%20Data%20Link%20.pdf)
---

## What is this?

A low-cost, lightweight **directional antenna controller** that improves the wireless data link between a UAV and its Ground Control Station (GCS). Instead of a mechanical rotating antenna, the system uses a **four-sector smart antenna array** electronically switched by a microcontroller — no moving parts, no mechanical wear.

The controller reads real-time GPS, compass, and altitude data to compute the UAV's bearing relative to the GCS, then switches to whichever antenna sector gives the strongest signal — all within 100 ms.

---

## How it Works

```
UAV in flight
     │
     ▼
[GPS + Compass + Altimeter]
     │  real-time position & heading
     ▼
[ESP32-S3 Microcontroller]
     │  computes bearing to GCS
     │  selects best antenna sector
     ▼
[SP4T RF Switch]
     │
     ├──► North Antenna
     ├──► East  Antenna
     ├──► South Antenna
     └──► West  Antenna  ──► GCS
```

---

## Hardware

| Component | Part |
|---|---|
| Microcontroller | ESP32-S3 DevKitC-1 |
| RF Switch | Analog Devices EV1HMC241AQS16 (SP4T) |
| Directional Antennas (×4) | Sevskiy AN220201-03C Log-Periodic |
| GPS | u-blox NEO-M8N |
| Compass | Memsic MMC5983MA |
| Altimeter | Adafruit BMP390 |
| Power Supply | MB102 + 2× 18650 Li-ion |

---

## Key Results

- ✅ Antenna switching latency: **~100 ms** (requirement: ≤ 500 ms)
- ✅ Front-to-back ratio: **~12.7 dB** (requirement: ≥ 12 dB)
- ✅ All sensor verification tests passed (GPS, compass, altimeter)
- ✅ All four antenna sectors verified via LED test and SDR measurement

---

## For More Details
Everything — full design specs, component selection analysis, circuit diagrams, test cases, cost breakdown, and Gantt chart — is in the 📄 [CEN493 Directional Antenna Controller for UAV Data Link](./CEN493%20Directional%20Antenna%20Controller%20for%20UAV%20Data%20Link.pdf).

