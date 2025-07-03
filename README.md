# 🚗 Real-Time Dynamic Parking Price Optimization

A real-time pricing system for urban parking lots that uses **streaming data** to dynamically adjust prices based on demand, traffic conditions, and competitor lots. The project visualizes pricing for each lot in **real-time using Bokeh**.

---

## 📦 Tech Stack Used

| Category         | Tools / Frameworks            |
|------------------|-------------------------------|
| Programming      | Python 3.x                    |
| Streaming Engine | [Pathway](https://pathway.com) |
| Visualization    | [Bokeh](https://bokeh.org)     |
| Data Analysis    | Pandas, TQDM                  |
| IDE              | Google Colab / Jupyter        |
| File Formats     | CSV, JSONL                    |

---

## 🧠 Project Overview

This capstone project focuses on building and comparing **three pricing models**:

### ✅ Model 1 – Baseline Model
A simple static pricing model which assigns a flat rate to all parking lots (e.g., ₹10/hr).

### ✅ Model 2 – Demand-Based Dynamic Model
Factors considered:
- Occupancy ratio (Occupancy / Capacity)
- Queue length
- Traffic condition (Low / Average / High)
- Vehicle type (Car, Bike, Truck)
- Special day flag

### ✅ Model 3 – Competitive Pricing Model
Enhances Model 2 by:
- Comparing with nearby lots using latitude and longitude
- Applying 5% premium if the current lot has higher demand

---

## 🧭 Architecture Diagram

```mermaid
flowchart TD
    A[CSV Input File: dataset.csv] --> B[Pathway Streaming Engine]
    B --> C[Model 1 - Baseline]
    B --> D[Model 2 - Demand-Based]
    B --> E[Model 3 - Competitive]
    C & D & E --> F[Price Output (JSONL)]
    F --> G[Bokeh Visualization Dashboard]
```

---

## 📊 Visualization

- Uses **Bokeh** for plotting real-time prices.
- Each model's output is streamed live and displayed.
- Plots update every 2 seconds over a window (e.g., 30 seconds).

---

## 📝 Instructions to Run

### 🧩 Step 1: Install Required Packages
```bash
pip install pathway bokeh pandas tqdm
```

### 📂 Step 2: Prepare Input Data
Upload `dataset.csv` into the same directory as your notebook or script.

### ▶️ Step 3: Run Notebook
- Load the dataset with `pd.read_csv()`.
- Implement the models using `apply()` for Pandas or `@pw.udf` for Pathway.
- Save results to `output.jsonl`.

### 📈 Step 4: Start Visualization
```python
show_realtime_plot(refresh_seconds=2, duration=30)
```

This function renders a live Bokeh plot of parking prices by lot and time.

---

## 🧾 Folder Structure

```
📦 parking-price-optimizer/
 ┣ 📄 main.ipynb               ← Full working notebook
 ┣ 📄 dataset.csv              ← Input CSV file
 ┣ 📄 output.jsonl             ← Output file from Pathway
 ┣ 📄 README.md                ← This file
 ┗ 📄 Parking_Pricing_Capstone_Report.pdf       ← (Optional) Detailed report
```

---

## 📗 Optional: Report

Dynamic Parking Price Optimization Using Streaming and Bokeh
👩‍💻 Submitted by: SYED SEEFATUL HAQUE
📅 Date: 03-07-2025
1. Abstract
This project presents a real-time parking price optimization system using streaming data. We developed three pricing models—Baseline, Demand-Based, and Competitive—and visualized them with Bokeh for interactive analysis. Using Pathway for real-time streaming, our solution simulates how urban parking lots can dynamically adjust pricing to maximize efficiency and revenue.
2. Introduction
Urban parking is a critical challenge due to fluctuating demand, special events, and uneven distribution of traffic. Static pricing often leads to inefficient use of space and user dissatisfaction. This project implements dynamic pricing strategies using real-time data to improve parking lot utilization.
3. Dataset Overview
We used a dataset simulating real-time streaming of parking lots with the following columns:

- ID: Unique parking lot identifier
- SystemCodeNumber: System-assigned code
- Capacity: Total parking spaces
- Occupancy: Number of occupied spaces
- Latitude, Longitude: Geolocation
- QueueLength: Vehicles waiting
- TrafficConditionNearby: Traffic descriptor (low, average, high)
- VehicleType: Car, Bike, Truck
- IsSpecialDay: 1 if special day
- LastUpdatedDate, Time: Timestamps
4. Model 1 – Baseline Fixed Pricing
This model assigns a constant price to all lots (e.g., ₹10 per hour). It serves as a reference for comparison with dynamic approaches.

- Logic: Fixed price = 10
- Pros: Simple
- Cons: Ignores real-time conditions
5. Model 2 – Demand-Based Dynamic Pricing
Prices are dynamically adjusted based on:
- Occupancy Ratio
- Queue Length
- Traffic conditions
- Special day flag
- Vehicle type
Equation:
price = α * (Occupancy / Capacity) + β * QueueLength - γ * Traffic + δ * SpecialDay + ε * VehicleWeight
6. Model 3 – Competitive Pricing Strategy
This model uses geolocation to price a lot based on nearby competitors.

- Calculates average Model 2 price of nearby lots within 0.01° radius
- Adds 5% markup on the local average
- Falls back to Model 2 price if no nearby lots
7. Visualizations
We used Bokeh for real-time visualization of pricing across lots. Charts were refreshed using `show_realtime_plot()` for a live dashboard feel.
8. Comparison Table
Sample comparison (customize with real output):
Lot ID	Model 1 Price	Model 2 Price	Model 3 Price
0	₹10	₹13.7	₹14.2
1	₹10	₹14.1	₹14.5
9. Conclusion
Model 2 and 3 significantly outperform the baseline by adapting to real-time and local conditions. Model 3 offers smarter pricing by factoring in competition. Future extensions could include:
- Integration with real-time traffic APIs
- Dynamic re-learning of pricing coefficients
- Mobile alerts for users
---

## ✍️ Author

- **Name**: SYED SEEFATUL HAQUE
- **Branch**: ARTIFICIAL INTELIGENCE & DATA SCIENCE
- **Year**: 4th Year
- **Institute**: GLBITM, GREATER NOIDA

---

## ✅ Deliverables

- [x] Google Colab notebook with code
- [x] Models 1, 2, 3 implemented
- [x] Real-time Pathway integration
- [x] Bokeh visualizations working
- [x] JSONL output
- [x] Architecture Diagram
- [x] README.md
- [ ] *(Optional)* Report PDF

---

## ⭐ Final Note

> “The goal is to create a fair, efficient, and real-time pricing system using real-world streaming data and visual tools.”

Don’t forget to ⭐ star the repo if you found it helpful!