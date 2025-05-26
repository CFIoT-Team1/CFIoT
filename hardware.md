# 🔧 Hardware Overview

This enclosure houses the core components for measuring and transmitting energy data. The setup is securely mounted on a cabinet and designed for stable, long-term monitoring.

## 🔍 Functional Overview

This energy monitoring system is built around a DIN-rail-mounted power meter that measures electrical parameters such as voltage, current, and power. It transmits this data wirelessly to a cloud platform via Wi-Fi. The system is fully enclosed for safety and reliability.

### System Responsibilities and Hardware Mapping

- **Integrated Measurement and Processing Unit**  
  → **Component: Adtek CPM-12D**  
  Measures electrical values directly from the circuit, processes the data internally, and displays real-time values on its screen. Communicates over RS485.

- **Communication Module**  
  → **Component: ZQWL-GE300D RS485-to-Wi-Fi dongle**  
  Sends processed data wirelessly to the cloud using the Modbus RTU protocol over RS485.

- **Power Supply**  
  → **Component: DIN Rail Power Supply** *(model unspecified)*  
  Delivers regulated DC voltage to all components. Powered directly from the measured circuit.

- **Relay Control**  
  → **Component: RT10-32X Relay (10A)**  
  Used to control a connected load or simulate switching behavior. Can be triggered automatically based on measurement conditions or manually.

---

## 🧩 Bill of Materials

| Component | Description |
|----------|-------------|
| **Adtek CPM-12D** | Multifunction power meter with local display and RS485 output. |
| **ZQWL-GE300D** | Wi-Fi dongle for wireless Modbus communication. |
| **RT10-32X Relay (10A)** | Electromagnetic relay for load control or simulation. |
| **DIN Rail Power Supply** | Supplies DC power to all devices in the enclosure. |
| **Wiring + Terminal Blocks** | Organized wiring and modular connections. |
| **Transparent Protective Enclosure** | Ensures physical safety and visibility. |

---

## 🖼️ System Images

### 📷 Full Enclosure

![Enclosure Overview](./images/enclosure_full.jpg)

### 🔍 Internal Wiring Close-Up

![Internal View](./images/enclosure_internal.jpg)

### 🧾 Presentation Slide (Measurement & Control Breakdown)

![Slide](./images/midterm_slide.png)

---
