#  Array Button: Intelligent Workforce & Inventory Ecosystem

![Status](https://img.shields.io/badge/Status-Prototype%20(PoC)-orange)
![Architecture](https://img.shields.io/badge/Architecture-Distributed%20AIoT%20%7C%20Edge%20Computing-blueviolet)
![Stack](https://img.shields.io/badge/Tech-ESP32%20%7C%20Pi%20Zero%20%7C%20Python%20%7C%20Whisper-blue)

**Array Button** is an advanced **Enterprise Situational Awareness System** that transcends traditional inventory tracking. It functions as a high-level operational intelligence layer—effectively a **cognitive communication network**—that connects physical assets with human workflow in real-time.

> **Transforming Noise into Intelligence:** Array Button turns the chaotic acoustic environment of a job site into structured, actionable business intelligence. Every command spoken is a data point saved, analyzed, and optimized for efficiency.

---

##  The Main Agenda

While currently prototyped as a voice-enabled inventory logger, the final vision of Array Button is a comprehensive **Workforce Intelligence Platform** designed for firms where "deskless" employees operate in complex environments.

### Core Capabilities
* Hyper-Personalized Monitoring:** Moving beyond generic logs, the system builds unique activity profiles for every employee (e.g., *"Shreyas is 40% ahead of schedule on steel framing"*).
* Automated Progress Reporting:** Eliminates manual status meetings. The system listens to ongoing tasks and auto-generates **End-of-Day (EoD) Reports**, flagging bottlenecks instantly.
* Live Status Tracking:** Provides managers with a real-time "Pulse" of the floor knowing exactly who is working on what, where they are, and their resource needs without a single phone call.
*  Predictive Resource Allocation:** Analyzes workforce patterns to predict inventory shortages *before* they stop production.



## System Architectures

Array Button is designed to be hardware-agnostic, supporting two distinct architectural approaches depending on the deployment environment: **Distributed AIoT** (Current) and **Heavy Edge** (Alternative/Future).


###  Architecture A: Distributed AIoT (The "Hive Mind")
* **Current Implementation (PoC)**
* **Philosophy:** "Dumb Ears, Smart Brain." Low-cost nodes stream raw audio to a central server for heavy processing.
* **Hardware:** * **Nodes:** ESP32 (DevKit V1) & ESP32-C3 (SuperMini).
    * **Microphones:** I2S Mics (INMP441 / ICS-43434).
    * **Server:** MacBook M-Series / PC (Python Backend).
* **Software Stack:**
    * **Firmware:** C++ (Arduino), WebSockets.
    * **AI Pipeline:** Vosk (Wake Word) → OpenAI Whisper (STT) → RapidFuzz (Logic).
    * **Latency:** < 200ms Wake Word response.
* **Pros:** Extremely low cost per node ($5), centralized updates, high-accuracy transcription via server-grade GPUs.

###  Architecture B: Heavy Edge (The "Autonomous Unit")
* **Alternative / High-Reliability Setup**
* **Philosophy:** "Smart Edge." Each node is a self-contained computer capable of processing voice locally without a central server.
* **Hardware:**
    * **Core:** Raspberry Pi Zero 2 W.
    * **Audio:** INMP441 I2S Microphone.
    * **Thermal:** Active Cooling (Fan + Heatsink) for sustained load.
* **Software Stack:**
    * **AI Pipeline:** **Vosk Medium Model** running locally on-device.
    * **Connectivity:** WiFi (Current) → **LoRa (Future)**.
* **Future Integration:** This architecture is designed for sites *without* WiFi coverage. Future iterations will integrate **LoRaWAN** transceivers to transmit processed text data over kilometers to a central gateway, enabling true off-grid situational awareness.


##  Tech Stack & Features

| Component | Distributed AIoT (ESP32) | Heavy Edge (Pi Zero 2 W) |
| :--- | :--- | :--- |
| **Processor** | Xtensa® Dual-Core 32-bit LX6 | Quad-core 64-bit ARM Cortex-A53 |
| **Wake Word** | Vosk Small (Server-side) | Vosk Small/Medium (On-Device) |
| **Transcription** | **OpenAI Whisper (High Fidelity)** | Vosk / PocketSphinx (Edge Optimized) |
| **Connectivity** | WebSockets (WiFi) | WiFi / **LoRa (Planned)** |
| **Power** | 0.2 Watts | 1-2 Watts |
| **Use Case** | Indoor / WiFi-covered Zones | Remote / Large-scale Sites |

---

##  Roadmap: From Prototype to Product

The current implementation serves as a **Proof of Concept (PoC)** validating the distributed acoustic architecture. The roadmap transitions this into a fully integrated **Industrial IoT (IIoT) Product**.

1.  **Contextual AI (Gemini 1.5 Pro):** Injecting logs into LLMs to generate narrative reports (e.g., *"Why is cement usage 20% higher today?"*).
2.  **Safety Compliance:** Training models to detect acoustic anomalies like distress calls, machinery failure sounds, or falling debris.
3.  **Biometric Integration:** Combining voice ID with wearable health data for fatigue monitoring.
4.  **LoRa Mesh Network:** Implementing the Architecture B communication layer for multi-kilometer range on construction sites.

---

##  Contributors

* **Shreyas Rai** 
* **Likith K** 
* **Manoj** 

---

*Array Button is not just a tool; it is the operating system for the deskless workforce.*

https://github.com/user-attachments/assets/179c4f57-d00e-430d-af88-2e1acee82cbc
