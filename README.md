# MFDConnect — Work in Progress

> **Universal tactical MFD for Microsoft Flight Simulator 2024**
> Hardware-first · Native Windows application · Currently in active development

**MFDConnect** is an experimental Multi-Function Display system designed primarily for **Microsoft Flight Simulator 2024** and the **WINCTRL / WinWing MFD + D1 display**.

The goal is not to reproduce a Garmin, G1000, or the avionics of a specific aircraft.

MFDConnect is being built as a **universal, modular and tactical MFD**, focused on situational awareness and designed around one core principle:

> **The hardware is the interface.**

The physical MFD controls the software.
No touchscreen. No mouse required in flight.

---

## 🎥 Development demos

> These videos show MFDConnect running during active development on the target hardware.
> UI, behavior and features shown here are **work in progress** and may change before V1.

### MFD demo
<img width="600" height="338" alt="mfdtest" src="https://github.com/user-attachments/assets/2094a611-d492-427f-b1a1-9f53c220da1d" />


### ENGINE demo

<img width="600" height="338" alt="mfdengtest" src="https://github.com/user-attachments/assets/277f86c9-f165-4a1c-b33b-ed737a24e79b" />

---

## 🚧 Current status

**MFDConnect is a work in progress.**

The project is already functional in several areas, but **V1 is not released yet**.

Current development focuses on building and validating the MFD experience on the physical D1 hardware before the project enters its stabilization and release phases.

### Current build

`0.16.7.x`

### Development status

| Area                       | Status                                    |
| -------------------------- | ----------------------------------------- |
| Core architecture          | Functional                                |
| SimConnect integration     | Functional                                |
| Hardware / HID             | Functional                                |
| Launcher                   | Functional · UI subject to major redesign |
| Layout Builder             | Functional                                |
| Keymap Builder             | Functional                                |
| HOME / physical navigation | Functional                                |
| HUD                        | Functional                                |
| MAP                        | Functional · physical validation ongoing  |
| ENGINE                     | Functional                                |
| Additional system pages    | In development                            |
| Stabilization              | Not started                               |
| Packaging / public V1      | Not started                               |

> **Functional does not mean final.**
> MFDConnect is under active development and several interfaces, workflows and visual elements will evolve significantly before V1.

---

# Hardware first

MFDConnect is currently designed around:

**WINCTRL / WinWing MFD**
**WINCTRL / WinWing D1 USB display**

The reference hardware provides:

* 44 physical buttons
* BRT encoder
* analog axis
* 3-position switch
* dedicated USB display

The D1 is exposed by Windows as a `768 × 1024` portrait display.

The physical MFD reveals a `768 × 768` working area inside that display.

MFDConnect renders directly into this space to make the software and physical hardware behave as a single instrument.

---

# A real MFD, not a desktop dashboard

The final MFD interface is designed to feel like **modern cockpit avionics**.

It takes inspiration from contemporary military and training aircraft without attempting to reproduce any specific cockpit.

The UI is built around:

* immediate readability
* physical softkeys
* contextual controls
* functional colors
* aircraft telemetry
* situational awareness
* minimal visual noise
* useful animations
* honest representation of available simulator data

Every color has a purpose.

Every control displayed around the screen corresponds to the physical hardware.

The MFD itself is not designed around clickable widgets.

---

# HUD

The HUD page provides a dedicated tactical flight presentation designed specifically for MFDConnect.

It is not intended to reproduce the HUD of a particular aircraft.

The objective is to provide essential flight and navigation information in a compact, immediately readable presentation suitable for the physical D1 display.

---

# MAP

MFDConnect includes its own mapping system rather than relying on aircraft avionics.

The current implementation is based around **MapLibre** with independent data providers.

Development currently includes:

* aircraft position
* navigation information
* multiple map layers
* terrain and geographic information
* tactical overlays
* 2D/3D rendering
* GeoLibre integration

The mapping architecture deliberately separates the rendering engine from the underlying data sources.

---

# Aircraft systems

MFDConnect is progressively introducing dedicated animated system pages.

The objective is not to display telemetry as tables.

Instead, aircraft systems should be understandable **at a glance** through gauges, diagrams, flows and state changes.

Current and planned presentations include:

**ENGINE**
Engine parameters, power, throttle, temperatures, pressures and operating state.

**FUEL**
Tanks, quantities, consumption, pumps, valves and fuel flow.

**ELECTRICAL**
Battery, generators, buses, connections and electrical distribution.

**HYDRAULICS**
Circuits, pumps, reservoirs, pressure and hydraulic consumers.

Only information actually available from the simulator is displayed.

MFDConnect does not invent missing aircraft data.

---

# Launcher

MFDConnect includes a native Windows configuration application used to prepare and control the MFD environment.

The current Launcher is **functional**, providing access to areas such as:

* displays
* hardware
* profiles
* MFD layouts
* diagnostics
* runtime/session configuration

Its current interface represents the present development state of the project, **not the intended final V1 experience**.

The Launcher UI/UX is expected to undergo a major redesign before release.

---

# Layout Builder

Different users and hardware configurations should not require hard-coded layouts.

The **Layout Builder** allows MFD pages and functions to be assigned to the physical MFD layout.

The resulting configuration becomes the source of truth used by the runtime.

---

# Keymap Builder

MFDConnect also includes a dedicated **Keymap Builder**.

Instead of treating physical buttons as arbitrary input numbers, configuration is centered around assigning application functions to physical controls.

This allows the same hardware controls to become contextual once a page is opened.

A button assigned to a main page from HOME can therefore expose page-specific functionality while that page is active.

---

# One simulator connection, multiple displays

The architecture is designed around a shared simulator state.

A single SimConnect connection feeds the MFD environment while individual MFD windows maintain their own runtime state.

The long-term architecture supports:

`0..n` independent MFD windows

without creating an arbitrary software limit on the number of displays.

---

# Where MFDConnect is going

The current priority is simple:

### V1 — Finish MFDConnect

Complete the original WINCTRL / WinWing + D1 implementation for Microsoft Flight Simulator 2024.

That includes final MFD pages, physical validation, stabilization, Launcher redesign and packaging.

### V2 — Multi-hardware

Once V1 is complete, the architecture can evolve toward other MFD hardware and generic configurations.

This may include resizable simulated MFD environments and support for community hardware adaptations.

### V3 — Multi-simulator

Future development may investigate support for other flight simulators such as:

* DCS
* X-Plane

These are future directions, **not V1 promises**.

---

# Why this page exists

MFDConnect is still being built.

This repository/page exists simply to show the project evolving:

**the hardware, the experiments, the UI, the working features and the progress toward V1.**

It is not a release page.

It is not documentation for installing MFDConnect.

It is a window into the development of the project.

---

## Work in progress

Features, interfaces and implementation details shown here may change before release.

Some parts are already running on the physical hardware.

Others are still being designed, implemented or validated.

**MFDConnect V1 is not available yet.**

---

### MFDConnect

**Microsoft Flight Simulator 2024**
**WINCTRL / WinWing MFD + D1**
**Windows · Native · Hardware-first**

*Built around the idea that the best cockpit interface is the hardware already under your fingers.*
