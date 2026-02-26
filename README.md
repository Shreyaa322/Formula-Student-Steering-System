# 🏎️ Formula Student Steering System : Data-Driven Design & Optimization

Steering system design, simulation, and optimization for a Formula Student EV.

> ⚠️ **Confidentiality Notice:** This repository documents the methodology and analytical
> approach only. Raw data, CAD files, specific parameters, and simulation outputs are
> confidential and not publicly shared.

>  **My Role:** Vehicle Dynamics Engineer — Steering Subsystem
>  COEP Technological University, Pune | 2024–2025

---

## 📌 Project Overview

The goal was to **design, optimize, and validate** a complete steering system for a Formula
Student electric race car, targeting optimal performance across two key dynamic events:
**Autocross** and **Skidpad** at FSG 2025.

The design process was entirely data-driven — from lap-time simulation and tyre data analysis
to iterative geometry optimization — ensuring every parameter decision was backed by
quantitative evidence rather than intuition.

---

## 🎯 Subsystem Objectives

- Minimize steering effort while maximizing tyre performance
- Achieve precise directional stability during sharp cornering
- Optimize geometry specifically for FSG Endurance & Skidpad track layouts
- Reduce weight through in-house manufacturing and material selection
- Ensure full compliance with Formula Student rules and regulations

---

## 🧠 Analytical Workflow
```
Lap-Time Simulation (OpenLap / MATLAB)
        ↓
Lateral Load Transfer Analysis
        ↓
Tyre Data Analysis (Magic Formula 6.1 — TTC Data)
        ↓
Steering Angle Computation (Inner & Outer Wheels)
        ↓
Line Geometry Definition (Front View & Top View)
        ↓
Kinematic Validation (MSC ADAMS Multibody Simulation)
        ↓
Component Design & Manufacture
```

---

## 📊 Key Analyses Performed

### 1. Lap-Time Simulation
- Used **MATLAB OpenLap** (point-mass simulation) to simulate vehicle behavior on
  Autocross and Skidpad track layouts
- Extracted lateral/longitudinal accelerations, vehicle speed, and slip angles at each
  track point — forming the quantitative basis for all geometry decisions

### 2. Lateral Load Transfer Analysis
- Computed dynamic and static load transfer under cornering using lateral acceleration
  data from lap-time simulation
- Determined ride frequencies, roll stiffness distribution, and wheel load variations
  across front and rear axles

### 3. Tyre Data Analysis — Magic Formula 6.1
- Processed **Tire Test Consortium (TTC)** tyre data using MATLAB's `mfeval`
  with the Magic Formula 6.1 model
- Plotted **Lateral Force (Fy) vs Slip Angle** and **Aligning Moment (Mz) vs Slip Angle**
  for all four wheels under event-specific loading conditions
- Extracted optimal slip angles for inner and outer front tyres to maximize cornering grip

### 4. Steering Angle & Geometry Selection
- Computed required front wheel angles using tyre force data and vehicle kinematic equations
- **Key Finding:** Hairpin turn required Pro-Ackermann geometry; Skidpad required
  Anti-Ackermann — impossible to satisfy both simultaneously with a single geometry
- **Decision:** Prioritized the Skidpad event (standalone scoring event) →
  **Anti-Ackermann geometry adopted**
- Steering ratio and C-factor calculated analytically from rack-pinion geometry

### 5. Bump & Roll Steer Optimization
- Front view line geometry optimized to minimize bump steer across the full
  jounce and rebound travel range
- Tie-rod positioned through the Instant Center of Rotation (ICR) of the
  wishbone assembly to achieve this

---

## ⚙️ System Design Summary

The steering system comprised the following subsystems, each designed with a focus
on weight reduction, manufacturability, and performance:

- **Rack & Pinion** — lightweight, modular, easy to assemble and service
- **Bevel Gear Assembly** — used to transmit force between upper and lower columns
  with a 1:1 ratio, reducing backlash and improving agility
- **Rack Housing** — multi-part aluminium housing for easy assembly/disassembly
- **Column Assembly** — upper and lower columns transmitting driver torque to the rack
- **Tie Rods & Steering Arms** — force transmission from rack to wheel assembly
- **Stopper Mechanism** — adjustable via shims, prevents linkage lock at full lock
- **Steering Wheel** — designed for hand ergonomics with high strength-to-weight
  composite construction
- **Steering Angle Sensor** — Hall-Effect rotary position sensor for data acquisition

---

## 🛠️ Tools & Software Used

![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=flat&logo=mathworks&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)

| Tool | Purpose |
|---|---|
| MATLAB + OpenLap | Lap-time simulation, load transfer, tyre data analysis |
| MATLAB mfeval (MF 6.1) | Magic Formula tyre modelling |
| CATIA | Steering & suspension line geometry development |
| MSC ADAMS | Multibody kinematic simulation & validation |
| Python | Data visualization — sensitivity plots, correlation matrices |
| Power BI | Comparative performance dashboards integrating simulation & telemetry |

---

## 🏁 Outcome

- Steering system successfully designed, manufactured (majority of components in-house),
  and validated through multibody simulation before physical build
- Anti-Ackermann geometry optimized for FSG Skidpad and Endurance events
- System fully integrated with suspension for kinematic compatibility
- Vehicle competed at **Formula Student Germany**, representing India

---

## 📄 Note on Data Availability

All simulation data, TTC tyre files, specific design parameters, CAD models, and
ADAMS outputs are confidential and not publicly shared. This repository documents
the engineering methodology and analytical process undertaken.
