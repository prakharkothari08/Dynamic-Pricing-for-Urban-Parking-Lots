
# 🅿️ Dynamic Pricing for Urban Parking Lots

This repository contains our implementation of dynamic pricing models for urban parking lots, developed as part of the **Summer Analytics 2025 Capstone Project** hosted by the **Consulting & Analytics Club × Pathway**.

The goal is to simulate a data-driven dynamic pricing system that adjusts parking fees based on real-time demand, traffic, and competitive factors. Our models help optimize parking space utilization in cities by preventing overcrowding and underutilization.

## 🚀 Project Overview

Urban parking is a limited resource, and static pricing often leads to inefficiency — lots are either overfilled or empty at various times. Our solution uses real-time data streams to:

- **Predict demand**
- **Adjust prices dynamically**
- **Suggest vehicle rerouting when needed**

### Implemented Models

1. **Baseline Linear Price Function**  
   Simple price adjustment based on current occupancy rate.

2. **Demand-Based Price Function**  
   Advanced pricing using occupancy, queue length, traffic, special day indicators, and vehicle type.

3. *(Optional for extension)* **Competitive Price Function**  
   Factor in nearby competitor prices using geospatial data.

---

## 🛠 Tech Stack

| Technology | Purpose |
|------------|---------|
| **Python (Pandas, Numpy)** | Data processing and model building |
| **Pathway** | Real-time data streaming and simulation |
| **Bokeh** | Real-time data visualization |
| **Google Colab** | Development environment |
| **GitHub** | Version control and collaboration |

---

## 🏗️ Project Architecture

```mermaid
flowchart LR
    subgraph Data Ingestion
        A1[Real-time data stream: occupancy, queue, traffic, etc.]
        A2[Pathway stream processor]
    end

    subgraph Pricing Engine
        B1[Baseline Linear Model]
        B2[Demand-Based Model]
        B3[Competitive Pricing (optional)]
    end

    subgraph Outputs
        C1[Dynamic Price Recommendations]
        C2[Visualizations via Bokeh]
        C3[Vehicle rerouting suggestions (optional)]
    end

    A1 --> A2
    A2 --> B1
    A2 --> B2
    A2 --> B3
    B1 --> C1
    B2 --> C1
    B3 --> C1
    C1 --> C2
    B3 --> C3
```

---

## 🔍 Detailed Architecture and Workflow

- **Data Ingestion**:  
  We use **Pathway** to simulate real-time streaming of parking lot data (occupancy, queue length, traffic, special day indicators, vehicle type). Data is processed at 30-minute intervals from 8 AM to 4:30 PM.

- **Pricing Models**:
  - **Baseline Linear Model**  
    Adjusts price linearly with occupancy:
    \[
    P_{t+1} = P_t + lpha rac{	ext{Occupancy}}{	ext{Capacity}}
    \]

  - **Demand-Based Model**  
    Uses weighted sum of features to compute normalized demand and update price smoothly:
    \[
    	ext{Demand} = lpha rac{	ext{Occupancy}}{	ext{Capacity}} + eta \cdot 	ext{QueueLength} - \gamma \cdot 	ext{Traffic} + \delta \cdot 	ext{IsSpecialDay} + \epsilon \cdot 	ext{VehicleTypeWeight}
    \]
    \[
    P_t = 	ext{BasePrice} \cdot (1 + \lambda \cdot 	ext{NormalizedDemand})
    \]
    where price is kept between 0.5× and 2× of the base price.

  - **Competitive Pricing (optional)**  
    Enhances pricing with competitive intelligence by:
    - Computing distance to nearby lots
    - Comparing competitor prices
    - Adjusting own price or suggesting rerouting

- **Visualization**:
  - Real-time Bokeh plots for price trends per lot.
  - Optional: comparison plots of competitor pricing.

---

## 📂 Repository Structure

```
├── Demand_Based_Price_Function_cleaned.ipynb  # Demand-based dynamic pricing notebook
├── Baseline_Linear_Price_Function_cleaned.ipynb  # Baseline linear pricing notebook
├── README.md  # Project documentation
├── data/  # Data files and simulated streams (if added)
└── images/  # (optional) Architecture diagrams, graphs
```

---

## 📌 How to Run

1. Open the notebooks in **Google Colab**.
2. Follow instructions in each notebook to run simulations and generate dynamic prices.
3. Visualizations will update in real-time using Bokeh.

---

## 📄 References

- [Pathway Docs: Real-Time App](https://pathway.com/developers/user-guide/introduction/first_realtime_app_with_pathway/)
- [Summer Analytics 2025](https://www.caciitg.com/sa/course25/)
- Project problem statement (see `problem_statement.pdf`)
