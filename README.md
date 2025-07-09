# 🅿️ Urban Parking Real-Time Dynamic Pricing System

## 🚗 Overview

Urban parking spaces are a scarce, high-demand commodity. This project simulates a **real-time dynamic pricing engine** for 14 urban parking lots based on:

- Historical usage
- Queue lengths
- Nearby traffic
- Special days (e.g., events, holidays)
- Vehicle type
- Competitor pricing and location

Prices are computed in real time via a streaming data pipeline, enabling smart, demand-sensitive pricing and rerouting suggestions.

---

## 🧰 Tech Stack

| Layer          | Tools Used                  |
|----------------|-----------------------------|
| Language       | Python                      |
| Real-time Engine | [Pathway](https://pathway.com)          |
| Visualization  | Bokeh                       |
| Data Handling  | Pandas, NumPy               |
| Geospatial     | Haversine Formula           |
| Environment    | Google Colab / Jupyter      |
| Documentation  | Markdown, Mermaid           |

---

## 🧱 Architecture Diagram

```mermaid
flowchart TD
    A[📥 CSV Input Data<br> (dataset.csv)] --> B[🔁 Pathway Streaming Engine]
    B --> C1[📊 Feature Engineering]
    C1 --> C2[🧠 Model 1<br> Baseline (Occupancy)]
    C1 --> C3[📈 Model 2<br> Demand-Based]
    C1 --> C4[🏙️ Model 3<br> Competitive + Rerouting]
    
    C2 --> D[📉 Real-Time Pricing Output]
    C3 --> D
    C4 --> D

    D --> E[📍 Bokeh Visualizations<br> per garage]
