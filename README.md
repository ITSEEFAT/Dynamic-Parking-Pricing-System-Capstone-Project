# Dynamic-Parking-Pricing-System-Capstone-Project
# 🅿️ Dynamic Parking Pricing System – Capstone Project

A real-time parking price optimization system that dynamically updates parking rates using live data streams and displays real-time pricing across models via dashboards.

---

## 🚀 Tech Stack

| Category         | Tools / Frameworks Used                        |
|------------------|-------------------------------------------------|
| Programming      | Python 3.x                                      |
| Data Streaming   | [Pathway](https://pathway.com/)                 |
| Visualization    | [Bokeh](https://docs.bokeh.org/en/latest/)      |
| Data Handling    | Pandas, TQDM                                    |
| Development      | Google Colab / Jupyter Notebook                 |
| Others           | JSONL, CSV, GitHub                              |

---

## 📐 Architecture Flow

### 🔁 **Real-Time Data Flow Pipeline**

```mermaid
flowchart LR
    A[CSV File (dataset.csv)] -->|Stream Input| B[Pathway Streaming Engine]
    B --> C[Model 1 – Baseline]
    B --> D[Model 2 – Demand-Based]
    B --> E[Model 3 – Competitive]
    C & D & E --> F[Output JSONL Stream]
    F --> G[Bokeh Live Dashboard]
