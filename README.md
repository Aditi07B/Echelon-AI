# EY Agentic AI — Automotive Aftersales Predictive Maintenance

## 📑 Table of Contents
- [Introduction](#-introduction)
- [Project Overview](#-project-overview)
- [Repository Structure](#-repository-structure)
- [System Architecture & Workflow](#-system-architecture--workflow)
- [Architecture Diagram](#-architecture-diagram)
- [Flow Chart](#-flow-chart)
- [Screenshots](#-screenshots)
- [Getting Started](#-getting-started)
- [Backend APIs](#-backend-apis)
- [Frontend Dashboard](#-frontend-dashboard)
- [Tech Stack](#-tech-stack)
- [About Us](#-about-us)

---

## 💡 Introduction

### Problem Statement
Automotive aftersales maintenance is largely reactive. Vehicles are serviced only after failures occur, leading to unexpected breakdowns, customer dissatisfaction, inefficient service center workloads, and delayed feedback to manufacturing teams.

### Solution
**EY Agentic AI — Automotive Aftersales Predictive Maintenance** introduces a production-grade, multi-agent AI system that continuously monitors vehicle telemetry, detects anomalies in advance, diagnoses issues, schedules service actions, gathers feedback, and generates actionable manufacturing insights through an autonomous LangGraph-driven workflow.

---

## 🚗 Project Overview

### Agents (LangGraph nodes)
ingest → anomaly detection (LSTM) → diagnosis → engagement → scheduling → feedback → manufacturing insights

### Model
PyTorch LSTM autoencoder for reconstruction-error–based temporal anomaly detection with configurable thresholds

### Data
**AgenticAI_Final_Format_Dataset.xlsx**
- 7-day telemetry  
- 30-minute intervals  
- 7 parameters per vehicle  

### Backend
FastAPI server executing the LangGraph workflow per vehicle and exposing REST APIs

### Frontend
Next.js + Tailwind dashboard (EY black/yellow theme) for monitoring, workflow visualization, and analytics

---

## 🗂 Repository Structure

```text
app/
 ├─ state.py
 ├─ config.py
 ├─ graph.py
 ├─ agents/
 ├─ models/
 │   └─ lstm_anomaly.py
 ├─ utils/
 │   └─ data_loader.py
api_server.py
requirements.txt
frontend/
 ├─ app/
 ├─ components/
 └─ types/
QUICKSTART.md
README_API.md
```

🔁 System Architecture & Workflow
How It Works

Data Ingest
Excel telemetry → load_vehicle_timeseries → raw_metrics per vehicle

LangGraph Workflow Execution
ingest → anomaly detection → diagnosis → customer engagement → service scheduling → feedback → manufacturing insights

Backend APIs
FastAPI runs workflows and exposes vehicle-level and fleet-level insights

Frontend Visualization
Next.js dashboard consumes APIs via proxy routes and renders fleet status, workflows, and analytics

🚀 Getting Started
Backend Setup
pip install -r requirements.txt
python api_server.py


Runs at http://localhost:8000

Requires AgenticAI_Final_Format_Dataset.xlsx in the project root

Frontend Setup
cd frontend
npm install
npm run dev


Runs at http://localhost:3000

Uses Next.js API routes to proxy requests to FastAPI

Set API_BASE_URL if backend URL differs

🔌 Backend APIs

GET / — Health check

GET /api/vehicles — Workflow results for all vehicles

GET /api/vehicles/{vehicle_id} — Single vehicle workflow

GET /api/stats — Aggregated fleet metrics

GET /api/manufacturing — Manufacturing and OEM insights

📊 Frontend Dashboard
Available Screens

Vehicle Dashboard
Fleet cards showing anomalies, diagnosis, service schedules, and feedback

Workflow Visualization
LangGraph pipeline with step-by-step execution status

Analytics & Insights
Charts (Recharts) and manufacturing insights tables

🧠 Tech Stack

Python / FastAPI — Backend APIs and orchestration

LangGraph — Multi-agent workflow framework

PyTorch — LSTM autoencoder for anomaly detection

Pandas / NumPy — Telemetry data processing

Next.js — Frontend framework

Tailwind CSS — EY black/yellow UI theme

Recharts — Data visualization

Hi, We are the makers of EY Agentic AI! 👋
About us

Meet the creators behind EY Agentic AI — Automotive Aftersales Predictive Maintenance — Aditi A, Aditi B, Arnav and Nikhil.
We are a passionate team focused on building intelligent, production-grade AI systems that solve real-world industry problems. This project reflects our interest in agentic AI, predictive analytics, and scalable system design, bringing together multi-agent orchestration, deep learning, and modern full-stack development.

Our goal is to design systems that move beyond reactive workflows and enable proactive, explainable, and data-driven decision-making for enterprises. Through this project, we explore how autonomous agents and temporal intelligence can transform traditional automotive aftersales into a smarter, connected ecosystem.

Aditi - Aditi Agale

Aditi - Aditi Bambal

Arnav - Arnav Parekar

Nikhil - Nikhil Parkar

Happy coding 💯

Made with love ❤️
## 🔁 **System Architecture & Workflow**

## **How It Works**

### **1. Data Ingest**
- **Excel telemetry**
- **load_vehicle_timeseries()**
- Converted into **raw_metrics** per vehicle

### **2. LangGraph Workflow Execution**
- **ingest → anomaly detection → diagnosis → customer engagement → service scheduling → feedback → manufacturing insights**

### **3. Backend APIs**
- **FastAPI** runs workflows
- Exposes **vehicle-level** and **fleet-level** insights

### **4. Frontend Visualization**
- **Next.js dashboard** consumes APIs via proxy routes
- Renders **fleet status**, **workflows**, and **analytics**

---

## 🏗 **Architecture Diagram**
<img width="512" height="371" alt="flow chart" src="https://github.com/user-attachments/assets/1fef14d8-3ba2-4a64-bc20-d0bb24273821" />

---

## 🔄 **Flow Chart**
<img width="512" height="339" alt="flow_chart" src="https://github.com/user-attachments/assets/161d8e8d-1572-46df-8a59-0ebc35ce10bb" />

---

## 🖥 **Screenshots**
<img width="512" height="232" alt="unamed" src="https://github.com/user-attachments/assets/81c541b3-f601-4050-a69b-4859793332b7" />
<img width="512" height="232" alt="unamed" src="https://github.com/user-attachments/assets/a9d3986b-7008-4e41-9591-05b27e663a0b" />

---

## 🚀 **Getting Started**

## **Backend Setup**
- `pip install -r requirements.txt`
- `python api_server.py`
- Runs at: **http://localhost:8000**
- Requires **AgenticAI_Final_Format_Dataset.xlsx** in project root

## **Frontend Setup**
- `cd frontend`
- `npm install`
- `npm run dev`
- Runs at: **http://localhost:3000**
- Uses **Next.js API routes** to proxy requests to FastAPI
- Set **API_BASE_URL** if backend URL differs

---

## 🔌 **Backend APIs**
- **GET /** — Health check
- **GET /api/vehicles** — Workflow results for all vehicles
- **GET /api/vehicles/{vehicle_id}** — Single vehicle workflow
- **GET /api/stats** — Aggregated fleet metrics
- **GET /api/manufacturing** — Manufacturing and OEM insights

---

## 📊 **Frontend Dashboard**

## **Available Screens**

### **Vehicle Dashboard**
- Fleet cards showing **anomalies**, **diagnosis**, **service schedules**, and **feedback**

### **Workflow Visualization**
- **LangGraph pipeline** with step-by-step execution status

### **Analytics & Insights**
- **Recharts-based charts**
- Manufacturing insight tables

---

## 🧠 **Tech Stack**
- **Python / FastAPI** — Backend APIs and orchestration
- **LangGraph** — Multi-agent workflow framework
- **PyTorch** — LSTM autoencoder for anomaly detection
- **Pandas / NumPy** — Telemetry data processing
- **Next.js** — Frontend framework
- **Tailwind CSS** — EY black/yellow UI theme
- **Recharts** — Data visualization

---

## 👋 **Hi, We are the makers of EY Agentic AI!**

## **About Us**
- Meet the creators behind **EY Agentic AI — Automotive Aftersales Predictive Maintenance**
- **Aditi A, Aditi B, Arnav, and Nikhil**

We are a passionate team focused on building **intelligent, production-grade AI systems** that solve real-world industry problems. This project reflects our interest in **agentic AI**, **predictive analytics**, and **scalable system design**, combining multi-agent orchestration, deep learning, and modern full-stack development.

Our goal is to move beyond **reactive workflows** and enable **proactive, explainable, and data-driven decision-making** for enterprises. Through this project, we explore how **autonomous agents** and **temporal intelligence** can transform traditional automotive aftersales into a smarter, connected ecosystem.

- **Aditi — Aditi Agale**
- **Aditi — Aditi Bambal**
- **Arnav — Arnav Parekar**
- **Nikhil — Nikhil Parkar**

---

## 💯 **Happy Coding**
**Made with love ❤️**
