# ⚡ Electric Meter Dashboard (Full Stack)

A full-stack electricity consumption dashboard system that integrates React front-end, Node.js + Express back-end, and Python-based CSV data processing.

## 🧩 Software System Components

[Software Documentation](software.md)

#### 🔹 1. React Frontend (`src/`)

Displays energy consumption charts:
- Total daily energy (summary)
- Hourly energy usage

**Buttons:**
- **Update Chart**: refreshes data from backend API `/api/hourly`
- **Run Python Script**: triggers data update via backend `/api/update-data`

#### 🔹 2. Node.js + Express Backend (`server.js`)

Serves 3 APIs:
- `GET /api/summary`: returns total daily kWh for each CSV
- `GET /api/hourly`: returns per-hour energy differences
- `POST /api/update-data`: triggers Python script to download/update CSVs

Also serves static files (like the front-end build) via `express.static()`

#### 🔹 3. Python Script (`scripts/download_data.py`)

Designed to:
- Read from remote AWS S3 bucket or local directory
- Download all `.csv` files in `main_branch_1/`
- Skip re-downloading unchanged files (based on LastModified timestamp)
- Output CSVs to `/public/main_branch_1/`

### 🚀 How to Run Locally

#### 1. Install Dependencies

```bash
npm install
pip3 install boto3
```

#### 2. Start the Backend

```bash
node server.js
```

This runs the Express API at `http://localhost:3001`

#### 3. Start the Frontend (in dev mode)

```bash
cd src
npm install
npm run dev -- --host
```

Then visit `http://localhost:5173`

### 📊 Data Flow

1. Frontend loads and fetches hourly/daily data via:
   - `GET /api/hourly`
   - `GET /api/summary`

2. User clicks "Run Python Script" button
   - Frontend sends `POST /api/update-data`
   - Backend executes `scripts/download_data.py`
   - Python script pulls files → saves to `public/main_branch_1/`
   - Frontend re-fetches new data and updates charts

### 🧪 Sample APIs

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/hourly` | Returns hourly energy deltas |
| `GET` | `/api/summary` | Returns total daily kWh per CSV |
| `POST` | `/api/update-data` | Triggers CSV download script |

### 👩‍🏫 For Presentations / Teaching

This project demonstrates:
- Full-stack integration with Python, JS
- Real-time data updates and visualization
- Hybrid local data processing model

**Use this project as a foundation to:**
- Add login/authentication
- Connect live IoT devices
- Export reports to PDF
- Automate Python job via cron

Feel free to extend or fork this dashboard. Contributions welcome!

---

**🛠️ Made with Python, Node.js, and React.**

![Dashboard Screenshot 1](https://github.com/user-attachments/assets/3d7307b3-61a5-4395-a906-dc6987c27d66)

![Dashboard Screenshot 2](https://github.com/user-attachments/assets/7a0d442d-7e1e-4502-a3dc-610ef2c362c7)



---
---

## 🛠️ Hardware Overview

[Hardware Documentation](hardware.md)

The project uses industrial-grade metering components for reliable real-time measurement:

| Component            | Description |
|---------------------|-------------|
| **Adtek CPM-12D**   | DIN-rail power meter. Measures voltage, current, power (kWh), and more via Modbus RTU. |
| **ZQWL-GE300D**     | RS485-to-Wi-Fi dongle. Sends data wirelessly to the backend. |
| **RT10-32X Fuse Holder** | Protects components by isolating overcurrent conditions. |
| **DIN Rail Power Supply** | Converts AC to regulated DC for powering the enclosure. |
| **Enclosure**       | Transparent DIN-rail case for clean wiring and modularity. |

---

## 💡 Problem & Solution

[Problem Statement](ProblemStatement.md)

### The Problem

Most users receive monthly power bills with **no detail on when or how energy was used**. This lack of feedback leads to unnecessary waste, especially in households and SMEs.

### The Solution

This dashboard provides **real-time energy visibility**, allowing users to:
- Identify consumption patterns
- Reduce costs through behavioral changes
- Align with energy-saving goals

Inspired by Taiwan's national net-zero efforts and the Smart City Expo.

### Use Cases

- **Homes** – Lower energy bills by changing small habits
-  **Labs** – Monitor equipment usage in real-time
- **Small Businesses** – Track peak demand and optimize load
-  **Workshops** – Identify high-consumption machinery

---

## 📣 Marketing Strategy
[Marketing Documentation](MarketingMaterial.md)

Our approach focuses on **closing the energy information gap** for everyday users and making energy data accessible and actionable.

### Key Differentiators
- **Low Cost** – Budget-friendly entry into energy monitoring
- **Ease of Use** – No manual reading, clear charts instead
- **Cloud-Connected** – View data from anywhere, anytime
- **Scalable Design** – Start with one meter, expand later
- **Integrated Power Supply** – Draws power directly from the circuit

### Target Audiences
- Rental property owners
- Budget-conscious households
- Schools and labs
- Small and medium-sized businesses (SMEs)
- Community centers and NGOs

### Promotion Methods
- **Education Campaigns**: highlight "invisible bill" frustration
- **Tangible Savings**: show how behavior changes save money
- **Digital Outreach**: social media, videos, real-world demos
- **Community Pilots**: partner with local landlords, institutions
- **Retail Channels**: online shops like Shopee / PC Home

---

## 👥 About Us

We are a team of five students from Taiwan Tech who built this project as part of the CFIoT course.

### Team Members

| Name                   | Role                | Responsibility                        |
|------------------------|---------------------|----------------------------------------|
| **Alan**               | Hardware Engineer    | Integrated sensors and enclosure       |
| **Paul**               | Software Engineer    | Backend and AWS integration            |
| **Lea**                | GitHub Engineer      | Codebase management                    |
| **Thisala**            | Creative Director    | Visual design and presentation         |
| **Abdullah**           | UI Engineer          | Designed the website                   |
---

## 🌐 Website

📎 Official site: [https://tunio399.wixsite.com/smart-power-meter](https://tunio399.wixsite.com/smart-power-meter)

---

