# Sentinel: Network Security Visualization & Analytics Dashboard

I built Sentinel to bridge the gap between heavy statistical data engineering and intuitive product design. Security logs are notoriously noisy and complex, making it difficult for stakeholders to interpret threats at a glance. 

This full-stack dashboard is designed to cut through that noise. It handles the heavy lifting on the backend—using distributed log ingestion and applying probability and time-series analysis to detect outliers. Then, it translates those mathematical anomalies into a clean, visually compelling React frontend. The ultimate goal of this project is to take raw, high-volume network traffic and turn it into an instantly readable data story.

## Motivation & Business Impact
In fast-paced, data-driven environments, raw data isn't enough; decision-makers need clear, reliable sources of truth. Sentinel was built with this product mindset. By abstracting away the complex database queries and statistical math, it empowers non-technical stakeholders to immediately understand the security posture of their network and take action based on clear visual evidence.

## The Data Story
Sentinel focuses on **data storytelling** by framing the analytics clearly:
1. **The Baseline:** It establishes a clear visual baseline of normal network traffic using a sleek, dark-mode time-series chart.
2. **The Anomaly:** It uses high-contrast, pre-attentive attributes (bright red markers) to immediately draw the user's eye to critical anomalies, such as massive spikes in payload sizes indicative of DDoS attacks.
3. **The Action:** It utilizes a background agent to instantly translate statistical deviations into digestible, actionable alerts.

## Technical Architecture

This project spans the entire Analytics Engineering stack, from data ingestion to UI component design.

### Frontend (Visualization & Application Design)
* **Framework:** React.js
* **Visualizations:** Recharts (chosen for its highly performant, accessible time-series data rendering).
* **UI/UX:** Focuses on clear typography, intentional color hierarchy, and interactive tooltips to translate raw API data into intuitive insights.

### Backend (Analytics Engineering & Distributed Systems)
* **API & Core:** Node.js and Express.js.
* **Distributed Systems:** Utilizes a Master-Executor architecture via Node's native `worker_threads` to simulate distributed, parallel ingestion and cleaning of high-volume network logs.
* **Database Systems:** Relational data storage using SQLite, serving dynamic API endpoints (`/api/traffic`, `/api/ingest`).
* **Machine Learning & Agentic Approaches:** * Implements time-series analysis using Z-Score statistical algorithms to flag predictive anomalies.
  * Features an autonomous background agent that continuously evaluates database anomalies and triages them by severity.

---

## How to Run Locally

You will need two terminal windows to run the frontend and backend simultaneously.

```bash
# --- TERMINAL 1: Start the Backend API ---
git clone [https://github.com/nolanefe/sentinel-dashboard.git](https://github.com/nolanefe/sentinel-dashboard.git)
cd sentinel-dashboard/backend
npm install
node server.js

# --- TERMINAL 2: Start the React Dashboard ---
# (Open a new terminal window in the same root folder)
cd sentinel-dashboard/frontend
npm install
npm start