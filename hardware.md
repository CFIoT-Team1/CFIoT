# 🔧 Hardware Overview

This enclosure houses the core components for measuring and transmitting energy data. The setup is securely mounted on a cabinet and designed for stable, long-term monitoring.

## 🧩 Components

| Component | Description |
|----------|-------------|
| **Adtek CPM-12D** | DIN-rail mounted multifunction power meter. Measures real-time voltage, current, and power consumption. Also includes a small display for direct readout. |
| **ZQWL-GE300D** | RS485-to-Wi-Fi dongle that transmits data from the power meter to the cloud. Uses Modbus RTU over RS485. |
| **RT10-32X Relay (10A)** | Provides switching or circuit isolation functionality. May be used for control or protection. |
| **DIN Rail Power Supply** | Supplies regulated DC power to the measurement and communication components. |
| **Wiring + Terminal Blocks** | For organized connections between sensor, relay, communication module, and power. |
| **Transparent Protective Enclosure** | Wall-mounted box ensures safety and visibility. |

## 🔌 Function Overview

- **Sensing:** The Adtek CPM-12D directly monitors electrical parameters.
- **Transmission:** The ZQWL-GE300D wirelessly sends data using Wi-Fi.
- **Relay Control (NOT SURE IF ACTUALLY USED!!!):** RT10-32X can allow load switching or safety control.
- **Power Supply:** All components receive power from the DIN power module.

---

> ⚠️ Note: There is **no ESP32** in this setup. The display seen in the enclosure belongs to the CPM-12D power meter.


