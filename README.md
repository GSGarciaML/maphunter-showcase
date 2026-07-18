# maphunter-showcase

**Detection engine that locates calibration maps inside undocumented ECU firmware** — the RPM × fuel-quantity tables that govern a diesel engine — with no symbol files and no map. Just bytes.
Scope: Bosch **EDC15 / EDC16**.



> ### 📄 Read the full case study → [**interactive dossier**](https://gsgarciaml.github.io/maphunter-showcase/)

---

## The problem

A calibration map is a grid of integers buried in hundreds of kilobytes of an ECU memory dump — **no headers, no names, no marked boundaries**. The engine has to nail three things at once:

- **Where** the map starts — the exact byte offset
- **What shape** it has — rows × columns
- **What** it represents — the function

And it has no oracle: in production there is no definition file to check against. Miss any of the three and a readable table turns into diagonal noise.

## What it produces

Real calibration maps recovered from production ECU firmware and rendered as 3D surfaces — a human-readable topography pulled straight out of raw bytes


## What this repository shows

This is a **measurement-driven** reverse-engineering project. The part I'm proudest of isn't an algorithm — it's the discipline that made progress possible in a problem where every idea *sounds* right:

- **A regression guardrail** over 8 firmware images with ground truth — no idea is adopted without a number beside it.
- **Reproducible ablations** — every behaviour change ships with a switch that restores the exact previous state.
- **A ledger of refuted hypotheses** — 21 ideas killed, each archived with the measurement that killed it (several of them mine).
- **Intellectual honesty** — two headline metrics published side by side, including the one that shows exactly where the pretty number lies.

## Results

| Metric | Value |
|---|---|
| Map localization (guardrail, 8 EDC16 images) | **74 %** |
| Real maps in the ground-truth corpus | **2 478** |
| ECUs analysed | **6** |
| Hypotheses refuted — and archived | **21** |

Per-ECU breakdown, methodology and one worked finding are in the **[case study](https://gsgarciaml.github.io/maphunter-showcase/)**.

## Skills demonstrated

`binary reverse engineering` · `empirical method under uncertainty` · `signal design` · `vectorised numerics (Python / NumPy)` · `corpus statistics on real automotive firmware`

---

> **The engine's source code is private.** This repository documents the problem, the method and the results — what the work demonstrates — without exposing the implementation.

**© 2026 Gonzalo Salceda García. All rights reserved.** Portfolio repository; source code private.



