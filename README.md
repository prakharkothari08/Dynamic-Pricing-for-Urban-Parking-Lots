# 🚗 Dynamic Pricing for Urban Parking Lots

A capstone project for **Summer Analytics 2025** by the **Consulting & Analytics Club × Pathway**  
Developed using **Python, Pandas, NumPy, Pathway, and Bokeh**

---

## 📌 Overview

Urban parking lots often use **static pricing**, which causes **overcrowding or underutilization**. This project solves that by implementing **dynamic pricing models** that adapt in real-time using historical and live data.

 Ibuilt:
- A **Baseline Linear Model**
- A **Demand-Based Pricing Model**

Real-time inputs such as **occupancy, queue, traffic, special events, and vehicle type** are used to calculate **demand** and **adjust prices** accordingly.

---

## 🛠️ Tech Stack

| Component        | Tools/Libraries                     |
|------------------|-------------------------------------|
| Programming      | Python 3.x                          |
| Data Handling    | Pandas, NumPy                       |
| Visualization    | Bokeh (for real-time plotting)      |
| Real-time Engine | [Pathway](https://pathway.com/)     |
| Notebook Env     | Google Colab / Jupyter Notebooks    |

---

## 🧱 Architecture Diagram

```mermaid
flowchart TD
    A[CSV Input Data (73 days)] --> B[Preprocessing & Feature Engineering]
    B --> C1[Baseline Linear Model]
    B --> C2[Demand-Based Pricing Model]
    C1 --> D[Real-Time Price Calculation]
    C2 --> D
    D --> E[Bokeh Visualization]
    D --> F[Price Output Stream via Pathway]
    subgraph Optional Extensions
        G[Competitive Pricing Model]
        G --> D
    end
