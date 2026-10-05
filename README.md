# ResPlast — Automated IoT Pyrolysis Monitoring & Control System

![License](https://img.shields.io/badge/license-MIT-green.svg)
![React](https://img.shields.io/badge/Frontend-React.js_(Vite)-61DAFB?logo=react)
![Firebase](https://img.shields.io/badge/Auth%20%26%20Realtime-Firebase-FFCA28?logo=firebase)
![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?logo=mysql)
![Arduino](https://img.shields.io/badge/Hardware-Arduino-00979D?logo=arduino)

> An end-to-end Automated IoT System designed to monitor, control, and analyze the thermal decomposition of plastic waste via high-temperature pyrolysis for fuel and material recovery.

---

## Project Overview

Plastic recycling via pyrolysis requires strict thermal regulation, continuous safety monitoring, and precise mass yield calculation. **ResPlast** integrates an embedded hardware control circuit with a modern web dashboard built with **React (Vite)**, using a hybrid data architecture (**MySQL** for structured local telemetry logging and **Firebase** for realtime synchronization and authentication).

The system automates chamber temperature management, continuously checks safety thresholds (gas and flame detection), and measures pre/post-process mass yield.

---

## Tech Stack & Hardware Architecture

### **Hardware & Embedded Subsystem**
* **Microcontroller:** Arduino MCU (C/C++)
* **Sensors:**
  * **K-Type Thermocouple:** High-temperature reactor monitoring.
  * **DHT11:** Ambient temperature and humidity inside the control circuit.
  * **Gas Sensor (MQ Series):** Combustible/toxic gas leakage detection.
  * **Flame Sensor:** Direct fire and thermal breach detection.
  * **Load Cell / Mass Sensor:** Weight measurement of plastic input vs. solid residue output.
* **Actuators & Control:**
  * **Dual Ventilation System:** Intake and exhaust fans for control box thermal regulation.
  * **Solenoid Valve / Actuator:** Automatic gas intake cutoff mechanism to stabilize ideal heating chamber temperatures.

### **Software & Cloud Architecture**
* **Frontend:** React.js (powered by Vite)
* **Authentication & Real-time Sync:** Firebase Auth & Firebase Realtime Database
* **Local Database:** MySQL (Historical sensor telemetry and process batch logging)
* **Hardware-Software Bridge:** Serial/WebSockets communication protocol for hardware-to-cloud telemetry sync.

---

## Key Features

* **Real-time Telemetry & Monitoring:** Live updates of reactor status, ambient conditions, and safety indicators via Firebase.
* **Mass Balance & Yield Calculation:** Pre-process and post-process weight comparison to evaluate pyrolysis conversion efficiency.
* **Closed-loop Temperature Regulation:** Actuator control over gas intake valves to maintain ideal thermal thresholds inside the heating chamber.
* **Active Safety Protocols:** Instant automatic shutdown triggers upon flame detection or abnormal gas buildup.
* **Historical Sensor Analytics:** Structured local MySQL data storage for offline batch audit and process optimization.

---

## System Architecture
[ Pyrolysis Reactor / Mass Chamber ]
│
[ Sensors (Thermocouple, DHT11, Gas, Flame, Weight) ]
│
[ Arduino MCU ]
│         │
│ (Gas/Fan Control)
▼         ▼
[ Actuators ]  [ Hardware-Software Bridge ]
│
┌────────────┴────────────┐
▼                         ▼
[ MySQL DB ]            [ Firebase Services ]
(Local Telemetry Log)     (Realtime Data & Auth)
│
▼
[ React (Vite) Dashboard ]
---

## Key Engineering Challenges & Solutions

* **Hybrid State Synchronization:** Combining offline local logging (MySQL) with real-time web monitoring (Firebase) ensured continuous operations during network outages without losing telemetry data.
* **Closed-Loop Thermal Safety:** Automated gas cutoff actuators reduced human intervention while maintaining chamber thermal stability within optimal pyrolysis parameters.

---

## Getting Started

### Prerequisites
* **Node.js:** `>= v18.x`
* **MySQL Server:** `>= v8.0`
* **Firebase Project:** Configured with Authentication and Realtime Database/Firestore.
* **Arduino IDE:** `>= v2.0` with required hardware libraries.

Author
Alexander Aaron Molina Serrano

Systems Engineer | Full-Stack & Embedded Systems Developer

LinkedIn: https://www.linkedin.com/in/alexander-aaron-molina-serrano-b70a07207/

GitHub: https://github.com/Angelwar616

