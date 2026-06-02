# Parking Management System

Parking Management System developed for the Siemens S7-1200 PLC and simulated using the HMI KTP700 Basic. 

## 🛠️ Tech Stack

* **PLC:** Siemens S7-1200 (AC/DC/Rly)
* **HMI:** 700 Basic
* **Language:** Ladder Diagram (LD)
* **Software:** TIA Portal

---

## 🚀 Key Features

* **Dynamic Space Counting:** Real-time monitoring of available spaces (0-6) with automatic entry block when full.
* **HMI Cinematic Simulation:** Smooth animations for gate movements and vehicle transit using precise offset counters.
* **Integrated Safety:** Software interlocks for gate motors (opening/closing protection) and thermal overload simulation.
* **Diagnostic Test Panel:** Virtual HMI controls to instantly fill, empty, or reset the system for testing purposes.

---

## 🔌 PLC I/O Mapping

### Inputs
* **SB1 / SB2:** Entry / Exit request buttons
* **SQ1 / SQ4:** Vehicle presence sensors
* **SQ2, SQ3 / SQ5, SQ6:** Gate limit switches (Open/Closed)
* **B1 / B2:** Safety photocells
* **FR1 / FR2:** Motor thermal overload relays

### Outputs
* **KM1 / KM2:** Entry gate motor (Open/Close)
* **KM3 / KM4:** Exit gate motor (Open/Close)
* **HL1 - HL4:** Traffic status lights (Spaces Available / Parking Full)
* **HL5 / HL6:** Flashing warning lights for moving gates

---

## 📐 Program Structure Overview

The Ladder logic is organized into clean, commented segments covering:

1. **Gate Automation:** Controls motor activation based on sensor inputs, limit switches, and safety interlocks.
2. **Counter Logic (`CTUD`):** Manages the core occupancy count between 0 and 6, integrated with quick-test overrides.
3. **Signaling & Alarms:** Handles status indicators and flashes warning lights using system clock bytes (5 Hz).
4. **HMI Animation Engine:** Generates numerical offsets using a 10 Hz clock to drive fluid graphical movements on the screen.
