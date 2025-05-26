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
  → **Component: RT10-32X Relay**  
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

### Full Enclosure Setup
<img src="./images/enclosure_full.jpg" alt="Enclosure Full View" width="400"/>

> Wall-mounted view of the transparent protective enclosure housing all components.

---

### Internal Wiring & Components
<img src="./images/enclosure_internal.jpg" alt="Internal Wiring" width="400"/>

> Close-up of internal wiring and DIN-rail mounted modules.

---

### Power Meter: Adtek CPM-12D  
![Adtek CPM-12D](./images/Adtek.png)  
> Multifunction power meter that measures voltage, current, and power.

---

### Communication Dongle: ZQWL-GE300D  
![ZQWL-GE300D](./images/ZQWL.png)  
> RS485-to-Wi-Fi dongle used to transmit power meter data to the cloud.

---

### Relay: RT10-32X  
![RT10-32X](./images/RT18.png)  
> Relay used for switching or load simulation in the system.

---

### 📊 Wiring Diagram (Slide)
![Hardware Diagram](./images/Hardware_Diagram.png)  
> Midterm presentation slide showing the wiring and system layout.

