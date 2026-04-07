# Sentinel: Network Security Visualization & Analytics Dashboard

Sentinel is a full-stack dashboard designed to bridge the gap between heavy statistical data engineering and intuitive product design. In the security domain, logs are notoriously noisy and complex, making it difficult for stakeholders to identify critical threats at a glance.

This platform handles the heavy lifting on the backend—utilizing distributed log ingestion and time-series analysis to detect outliers—and translates those mathematical anomalies into a clean, highly-interactive React frontend. The goal of this project is to transform raw, high-volume network traffic into actionable security intelligence.

## Motivation & Business Impact

In high-throughput environments, raw security data is often opaque. Decision-makers require high-fidelity sources of truth to respond to threats effectively. Sentinel was built with a product-centric mindset: by abstracting away complex database queries and statistical math, it empowers both technical and non-technical stakeholders to immediately understand their network's security posture and take action based on empirical evidence.

## Analytical Framework

Sentinel utilizes a three-stage analytical framework to optimize threat detection and response:

* **The Baseline:** Establishes a clear visual baseline of normal network traffic using a sleek, dark-mode time-series architecture.
* **The Anomaly:** Employs high-contrast, pre-attentive attributes (bright red markers) to draw immediate attention to critical anomalies, such as volumetric DDoS indicators.
* **The Action:** Leverages a background agent to translate statistical deviations into digestible, prioritized alerts for security operations.

## Technical Architecture

This project spans the entire Analytics Engineering stack, from data ingestion to UI component design.

### Frontend (Visualization & Application Design)
* **Language & Library:** JavaScript (ES6+), React.js
* **Visualizations:** Recharts (Chosen for its highly performant, accessible time-series data rendering).
* **UI/UX:** Focuses on clear typography, intentional color hierarchy, and interactive tooltips to translate raw API data into intuitive insights.

### Backend (Analytics Engineering & Distributed Systems)
* **API & Logic:** JavaScript (Node.js), Express.js
* **Distributed Systems:** Utilizes a Master-Executor architecture via Node's native `worker_threads` to simulate distributed, parallel ingestion and cleaning of high-volume network logs.
* **Database Systems:** Relational data storage using SQLite, serving dynamic API endpoints (`/api/traffic`, `/api/ingest`).
* **Machine Learning:** Implements time-series analysis using Z-Score statistical algorithms to flag predictive anomalies.
* **Agentic Automation:** Features an autonomous background agent that continuously evaluates database anomalies and triages them by severity.

## How to Run Locally

You will need two terminal windows to run the frontend and backend simultaneously.

```bash
# --- TERMINAL 1: Start the Backend API ---
git clone [https://github.com/nolanefe/sentinel-dashboard.git](https://github.com/nolanefe/sentinel-dashboard.git)
cd sentinel-dashboard/backend
npm install
node server.js

# --- TERMINAL 2: Start the React Dashboard (Open a new window/tab) ---
cd sentinel-dashboard/frontend
npm install
npm start
