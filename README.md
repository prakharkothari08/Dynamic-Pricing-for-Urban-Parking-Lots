# 🚗 Dynamic Pricing for Urban Parking Lots

A Capstone Project for **Summer Analytics 2025** hosted by the Consulting & Analytics Club × Pathway.

---

## 📌 Project Overview

Urban parking prices that remain static lead to inefficiencies like underutilization or overcrowding. This project builds dynamic, intelligent pricing models for 14 parking spaces based on real-time data using Python, Pandas, and Pathway.

---

## 📊 Models Implemented

### 🔹 Model 1: Baseline Linear Price Function
- Price increases linearly with occupancy
- Simple and interpretable
- Acts as a baseline reference

### 🔹 Model 2: Demand-Based Price Function
- Uses real-time features: Occupancy, Queue, Traffic, Events, Vehicle Type
- Builds a normalized demand function
- Smooth and bounded price changes
- More adaptable and realistic

---

## 🧠 Demand Function

```math
Demand = α * (Occupancy / Capacity) + β * QueueLength − γ * Traffic + δ * IsSpecialDay + ε * VehicleTypeWeight
