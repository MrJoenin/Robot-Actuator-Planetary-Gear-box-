# 🦾 70mm Robot Actuator Planetary Gearbox

**A compact 6:1 planetary gearbox designed for NEMA 17 stepper motors — built for robotic arm joints and modeled in SolidWorks.**

![Assembly Render](PHOTOS/[Full Assembly1.0].jpeg)
> 📸 *Replace the above line with your actual image path from the `/PHOTOS` folder.*

---

## 📌 Overview

This project is a fully custom-designed **70mm planetary gearbox** intended for robotic arm joint actuation. The gearbox mounts directly onto a **NEMA 17 stepper motor** and provides a **6:1 gear reduction**, multiplying output torque while maintaining a compact, coaxial form factor.

Planetary (epicyclic) gear systems are the preferred architecture for robotic joints due to their high torque-to-weight ratio, balanced load distribution across multiple gear meshes, and clean coaxial input/output alignment.

All parts were modeled in **SolidWorks** and are optimized for **FDM 3D printing** with PETG or PLA+.

> Built as part of an ongoing robotics and embedded systems engineering portfolio at NJIT.

---

## 🔩 Key Features

- **6:1 gear reduction** — 6x torque multiplication over the motor's native output
- **70mm outer diameter** — compact enough for most robotic arm linkage designs
- **NEMA 17 compatible** — drop-in mount for the most common stepper motor form factor
- **3-planet design** — balanced radial load, smooth output, minimal vibration
- **3D-print ready** — all STL files included; no machining required
- **SolidWorks native** — fully parametric `.SLDPRT` and `.SLDASM` files included

---

## 📐 Design Specifications

| Parameter | Value |
|---|---|
| Outer Diameter | 70 mm |
| Gear Ratio | 6:1 |
| Number of Planet Gears | 3 |
| Gear Type | Planetary (Epicyclic) |
| Motor Compatibility | NEMA 17 Stepper |
| Designed In | SolidWorks |
| Recommended Material | PETG or PLA+ |
| Manufacturing Method | FDM 3D Printing |

**Gear Ratio Verification:**
```
Gear Ratio = 1 + (Ring Teeth / Sun Teeth)
6 = 1 + (Ring Teeth / Sun Teeth)  →  Ring Teeth = 5 × Sun Teeth
```

---

## 📁 Repository Structure

```
Robot-Actuator-Planetary-Gear-box-/
│
├── cad/
│   ├── *.SLDPRT          # SolidWorks individual part files
│   └── *.SLDASM          # SolidWorks full assembly file
│
├── stl/
│   ├── sun_gear.stl      # Central input gear
│   ├── planet_gear.stl   # Orbiting planet gears (print x3)
│   ├── ring_gear.stl     # Fixed outer annulus gear
│   ├── planet_carrier.stl# Output shaft / carrier plate
│   └── housing.stl       # Outer gearbox housing
│
├── PHOTOS/
│   ├── render_assembly.png
│   ├── render_exploded.png
│   └── render_section.png
│
└── README.md
```

> ⚠️ *Update the STL filenames above to match the actual names in your `/stl` folder.*

---

## ⚙️ How It Works

A planetary gearbox has four main components:

| Component | Role |
|---|---|
| **Sun Gear** | Central input — driven by the motor shaft |
| **Planet Gears (×3)** | Orbit the sun gear; mesh with both sun and ring |
| **Ring Gear (Annulus)** | Fixed outer gear with internal teeth |
| **Planet Carrier** | Output shaft; rotates as planets revolve around the sun |

Motor torque drives the **sun gear** → planet gears roll along the fixed **ring gear** → the **planet carrier** (output) rotates at 1/6 the input speed with 6× the torque.

Using 3 planet gears equally distributes the radial load, resulting in:
- Higher efficiency than spur or worm gear equivalents
- Reduced stress on individual teeth
- Smoother, vibration-resistant output — critical for precise arm positioning

---

## 🖨️ Printing Guidelines

| Setting | Recommendation |
|---|---|
| Material | **PETG** (preferred) or PLA+ |
| Layer Height | 0.15 – 0.20 mm |
| Infill — Gears | 40–60% (gyroid or grid pattern) |
| Infill — Housing | 25–30% |
| Perimeters / Walls | 4+ for all gear components |
| Supports | Required for ring gear and housing |
| Part Cooling | Enabled for PETG (moderate fan speed) |
| Fit Tolerance | ±0.2 mm between mating surfaces |

> 💡 **Tips:**
> - Print gears **upright** so layer lines run perpendicular to tooth load direction
> - If planet gears feel tight, scale them to **99.5%** to compensate for printer expansion
> - PETG is recommended over PLA for joints under sustained load or heat exposure
> - Dry your filament before printing gears — moisture causes surface defects on gear teeth

---

## 🚀 Getting Started

### Option A — Edit in SolidWorks
1. Clone or download this repository
2. Open the `.SLDASM` file in **SolidWorks 2020 or later**
3. All part files will resolve automatically via relative paths

### Option B — Import into Another CAD Tool
1. Export `.STEP` files from SolidWorks (File → Save As → `.STEP`)
2. Import into **Fusion 360**, **Onshape**, **FreeCAD**, or any STEP-compatible tool

### Option C — 3D Print Directly
1. Download all `.stl` files from the `/stl` folder
2. Slice using **PrusaSlicer**, **Cura**, or **Bambu Studio**
3. Follow the printing guidelines above
4. Print **3 copies** of the planet gear

### Option D — Motor Integration
1. Align the gearbox housing with your NEMA 17 motor face plate
2. Secure with M3 bolts through the motor mounting holes
3. Press/slide the sun gear onto the motor shaft (5mm D-shaft)
4. Attach output load to the planet carrier shaft

---

## 🛠️ Tools & Software

| Tool | Purpose |
|---|---|
| SolidWorks | 3D CAD modeling & assembly |
| PrusaSlicer / Cura | Slicing STL files for FDM printing |
| FDM 3D Printer | Part fabrication |
| NEMA 17 Stepper Motor | Input drive |

---

## 📖 Background & Motivation

This gearbox was designed to solve a core challenge in robotic arm design: **NEMA 17 stepper motors deliver low torque at useful speeds**, making them insufficient for direct-drive joints under any meaningful load.

A planetary gearbox is the most mechanically efficient solution — outperforming spur gear trains (poor load distribution), worm gears (high friction, non-backdrivable), and belt drives (slippage, compliance) in the same footprint.

This project demonstrates skills in:
- Mechanical CAD design (SolidWorks — parts, assemblies, mates)
- Gear geometry and kinematic analysis
- Design-for-manufacture (DFM) for FDM 3D printing
- Tolerance analysis for moving mechanical assemblies
- Robotic actuator systems integration

---

## 🔮 Future Improvements

- [ ] Add output flange with standard M3 bolt circle pattern
- [ ] Integrate encoder mount for closed-loop position feedback
- [ ] Design dual-stage variant for higher reduction (e.g. 36:1)
- [ ] Evaluate Nylon/CF-Nylon printing for higher-load applications
- [ ] Publish measured efficiency and backlash test data
- [ ] Add parametric SolidWorks equations for custom gear ratios

---

## 📄 License

This project is open source under the **MIT License** — free to use, modify, and build upon with attribution.

---

## 👤 Author

**John** (MrJoenin)
- 🔗 GitHub: [@MrJoenin](https://github.com/MrJoenin)
- 🎓 Electrical & Computer Engineering Technology — NJIT
- 🤖 Minor in Drones & Robotics

---

*Found this useful or used it in a build? Drop a ⭐ on the repo — it helps others find it!*
