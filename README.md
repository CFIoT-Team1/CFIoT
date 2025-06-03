⚡ Electric Meter Dashboard (Full Stack with AWS Integration)

A full-stack electricity consumption dashboard system that integrates React front-end, Node.js + Express back-end, and Python-based AWS S3 data fetching.

📦 Project Structure

electric-meter-final-all-integrated/

├── server.js                   # Express.js backend server

├── scripts/

│   └── download_data.py       # Python script to pull CSV files from AWS S3

├── public/

│   └── main_branch_1/         # Folder containing downloaded CSV data

├── src/                       # React front-end source code

│   └── App.jsx                # Main dashboard component

├── package.json               # Project dependencies and scripts

└── README.md                  # This file

🧩 System Components

🔹 1. React Frontend (src/)

Displays energy consumption charts:

Total daily energy (summary)

Hourly energy usage

Buttons:

Update Chart: refreshes data from backend API /api/hourly

Run Python Script: triggers data update from AWS S3 via backend /api/update-data

🔹 2. Node.js + Express Backend (server.js)

Serves 3 APIs:

GET /api/summary: returns total daily kWh for each CSV

GET /api/hourly: returns per-hour energy differences

POST /api/update-data: triggers Python script to download CSVs from S3

Also serves static files (like the front-end build) via express.static()

🔹 3. Python Script (scripts/download_data.py)

Uses boto3 to:

Connect to AWS S3

Download all .csv files in main_branch_1/

Skip re-downloading unchanged files (based on LastModified timestamp)

Output CSVs to /public/main_branch_1/

☁️ AWS Integration (To Set Up Later)

AWS S3 Bucket stores CSV data uploaded from IoT/smart meters.

Example file path: s3://powerdata-test-1/main_branch_1/main_ami_20250327.csv

IAM key must be placed in the Python script (you should rotate and protect this key!)

🚀 How to Run Locally

1. Install Dependencies

npm install
pip3 install boto3

2. Start the Backend

node server.js

This runs the Express API at http://localhost:3001

3. Start the Frontend (in dev mode)

cd src
npm install
npm run dev -- --host

Then visit http://localhost:5173

📊 Data Flow

Frontend loads and fetches hourly/daily data via:

GET /api/hourly

GET /api/summary

User clicks "Run Python Script" button

Frontend sends POST /api/update-data

Backend executes scripts/download_data.py

Python script pulls files from S3 → saves to public/main_branch_1/

Frontend re-fetches new data and updates charts

🌐 How to Deploy on AWS (Tomorrow's Setup)

✅ Requirements:

AWS EC2 Ubuntu instance

Open ports:

SSH: 22

Backend API: 3001

Frontend Dev: 5173

Basic Steps:

# Install env
sudo apt update
sudo apt install -y nodejs npm python3-pip

# Upload project or git clone
cd electric-meter-final-all-integrated
npm install
pip3 install boto3

# Start backend
node server.js

# Build frontend
cd src
npm run build

Then set Express to serve /dist, or set up nginx reverse proxy.

🧪 Sample APIs

GET  /api/hourly        -> Returns hourly energy deltas
GET  /api/summary       -> Returns total daily kWh per CSV
POST /api/update-data   -> Triggers S3 download script

👩‍🏫 For Presentations / Teaching

This project demonstrates:

Full-stack integration with Python, JS, and AWS

Real-time data updates and visualization

Cloud + local computation hybrid model

Use this project as a foundation to:

Add login/authentication

Connect live IoT devices

Export reports to PDF

Automate Python job via cron

Feel free to extend or fork this dashboard. Contributions welcome!

🛠️ Made with Python, Node.js, and React.

