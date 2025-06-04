# ⚙️ Software Overview

## Purpose

This project provides a complete system for visualizing and analyzing electricity consumption using smart meter data. It offers a responsive, interactive dashboard that displays energy usage trends and allows users to update the dataset in real-time from cloud-stored CSV logs.

---

## Architecture

A modular full-stack application with three main components:

- **Frontend (React + Vite):** Interactive dashboard with charts, time range selection, and dark mode.
- **Backend (Express):** REST API for serving processed data and triggering updates.
- **Cloud Integration (AWS S3 + Python):** Syncs energy data in CSV format from an S3 bucket.


---

## Key Features

### Energy Diagram
- Hourly and daily consumption visualized.
- Select range: `1 day`, `7 days`, `30 days`.

### Cloud Sync
- Syncs data from AWS S3.
- Downloads only updated files.

### Visualization
- Line chart (Chart.js).
- Toggle dark/light mode.

---

## Stack

| Layer        | Technology                  | Purpose                                 |
|--------------|-----------------------------|-----------------------------------------|
| Frontend     | React, Vite, Tailwind CSS   | UI components and dashboard rendering   |
| Backend      | Node.js, Express.js         | REST API and CSV processing             |
| Cloud Sync   | Python, Boto3               | S3 integration for data fetching        |
| Charting     | Chart.js, react-chartjs-2   | Visualizing energy usage                |

---




