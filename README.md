# 🔬 Rigol MHO984 — An Honest Bench Review

**Status: 🚧 In progress — instrument received October 2026**

Real measurements on real boards: noise floor, 12-bit vs 8-bit, rise time, serial buses, signal integrity and near-field EMI. Every number in the article comes with its raw data and the script that produced it.

## 🤝 Disclosure — Collaboration commerciale

This review is a **commercial collaboration with [Eleshop](https://www.eleshop.eu)** (Eindhoven, NL). Eleshop sold me the MHO900-BND bundle with a 20% discount and free shipping.

Eleshop has no say on the measurements or the conclusions. The good, the bad and the limits are all reported. Raw data and scripts are published here so anyone can check them.

## 📐 What this review covers

- **Characterising the instrument**: noise floor, DC gain accuracy, Bode plot validation
- **12-bit vs 8-bit**: same bench, same signal, same day, against my old Hantek DSO2D15
- **Rise time & bandwidth**: measured with a 30–40 ps edge generator, not taken from the datasheet
- **Real boards**: power rail ripple, CAN bus, motor axes in mixed signal, ZVS driver
- **Near-field EMI**: FFT + near-field probes on a custom test board
- **Limits**: everything I could not verify, and why

## 🧰 Test setup

| Instrument | Model | Role |
|---|---|---|
| Oscilloscope (under test) | Rigol MHO984 (MHO900-BND bundle) | — |
| Oscilloscope (reference) | Hantek DSO2D15 | 8-bit comparison |
| Bench multimeter | OWON XDM1041 | DC gain reference |
| Pulse generator | *TBD* | Rise time, TDR |

## 🔌 Custom hardware

| Board | What it does |
|---|---|
| X2 low-impedance probe | AC-coupled, 100 Ω, for power rails and 50 Ω lines |
| EMI test board | Two 50 Ω microstrips, one over a cut ground plane |
| 50 Ω LP filter | Known reference to validate the Bode plot |

KiCad files are in [`hardware/`](hardware/).

## 📊 Progress

| Test | Status |
|---|---|
| First hands-on | ✅ |
| Noise floor table | ⏳ |
| 12-bit vs 8-bit | ⏳ |
| Bode plot validation | ⏳ |
| Rise time | ⏳ |
| Real boards | ⏳ |
| Near-field EMI | ⏳ |
| Article | ⏳ |

## 🗂️ Repository layout

```
rigol-mho984-review/
├── article.md      the review itself
├── images/         photos and screenshots
├── data/           raw CSV, dated
├── scripts/        SCPI acquisition and plotting (Python)
├── hardware/       KiCad projects of the custom boards
└── journal/        dated lab notebook
```

## 📜 License

© 2026 Malik Jenatton — All rights reserved.
Eleshop is allowed to publish and edit the article on its own website.
