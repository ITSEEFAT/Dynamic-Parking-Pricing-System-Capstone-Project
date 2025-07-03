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
📊 Visualization
Uses Bokeh for plotting real-time prices.

Each model's output is streamed live and displayed.

Plots update every 2 seconds over a window (e.g., 30 seconds).

📝 Instructions to Run
🧩 Step 1: Install Required Packages
bash
Copy
Edit
pip install pathway bokeh pandas tqdm
📂 Step 2: Prepare Input Data
Upload dataset.csv into the same directory as your notebook or script.

▶️ Step 3: Run Notebook
Load the dataset with pd.read_csv().

Implement the models using apply() for Pandas or @pw.udf for Pathway.

Save results to output.jsonl.

📈 Step 4: Start Visualization
python
Copy
Edit
show_realtime_plot(refresh_seconds=2, duration=30)
This function renders a live Bokeh plot of parking prices by lot and time.

🧾 Folder Structure
css
Copy
Edit
📦 parking-price-optimizer/
 ┣ 📄 main.ipynb               ← Full working notebook
 ┣ 📄 dataset.csv              ← Input CSV file
 ┣ 📄 output.jsonl             ← Output file from Pathway
 ┣ 📄 README.md                ← This file
 ┗ 📄 Parking_Report.pdf       ← (Optional) Detailed report
📗 Optional: Report
Describes the objective, dataset, model logic, implementation, and results.

Charts included for each pricing strategy.

Add screenshots of your Bokeh plot outputs.

✍️ Author
Name: Your Name

Branch: AIDS / CSE

Year: 4th Year

Institute: Your College Name

✅ Deliverables
 Google Colab notebook with code

 Models 1, 2, 3 implemented

 Real-time Pathway integration

 Bokeh visualizations working

 JSONL output

 Architecture Diagram

 README.md

 (Optional) Report PDF

⭐ Final Note
“The goal is to create a fair, efficient, and real-time pricing system using real-world streaming data and visual tools.”

Don’t forget to ⭐ star the repo if you found it helpful!
