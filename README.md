#  Supply Chain Optimization Analysis

A complete end-to-end Data Analytics project on supply chain performance using the **DataCo Smart Supply Chain Dataset**. The project includes Python-based EDA, data visualization, and an interactive Power BI dashboard.

---

##  Objective

Analyze supply chain data to:
- Identify the rate and causes of late deliveries
- Compare shipping mode reliability
- Understand regional delivery performance
- Evaluate profitability across product categories
- Build an interactive dashboard for business decision-making

---

##  Dataset

**Source:** [DataCo Smart Supply Chain Dataset (Kaggle)](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain)

| Property | Detail |
|---|---|
| Total Rows | 180,519 |
| Total Columns | 53 (14 used for focused analysis) |
| Data Type | Orders, Shipping, Delivery, Sales, Profit/Loss |

---

##  Tools & Technologies

| Purpose | Tool |
|---|---|
| Data Cleaning & Analysis | Python (Pandas, NumPy) |
| Data Visualization | Matplotlib, Seaborn |
| Interactive Dashboard | Power BI Desktop |
| Development Environment | VS Code + Jupyter Notebook |
| Version Control | GitHub |

---

##  Project Structure

```
supply-chain-analysis/
│
├── analysis.ipynb                  # Main Python analysis notebook
├── DataCoSupplyChainDataset.csv    # Raw dataset (180K+ rows)
├── clean_supply_chain.csv          # Cleaned dataset (14 key columns)
├── Supply_Chain_Dashboard.pbix     # Interactive Power BI Dashboard
└── README.md                       # Project documentation
```

---

##  Key Insights

### 1.  Late Deliveries — A Major Problem
> **54.8%** of all orders were delivered late — more than half the total order volume of 1,80,519 orders.

### 2.  Shipping Mode Reliability (Biggest Surprise!)

| Shipping Mode | Late Delivery Rate |
|---|---|
|  First Class | 95.3% |
|  Second Class | 76.6% |
|  Same Day | 45.7% |
|  Standard Class | 38.1% |

> **Counter-intuitive finding:** "First Class" — the premium shipping option customers pay extra for — has the **highest late delivery rate (95.3%)**! This is a critical service gap that directly impacts customer trust and retention.

### 3.  Late Delivery Is a Global, Systemic Issue

| Region | Late Delivery Rate |
|---|---|
| Central Africa | 57.9% |
| South Asia | 56.3% |
| East Africa | 55.9% |
| Western Europe | 55.8% |

> All regions show 48–58% late delivery rate — meaning the problem is **company-wide**, not region-specific. Root cause lies in internal processes, not geography.

### 4.  Top Sales Countries

| Rank | Country | Performance |
|---|---|---|
|  | USA (Estados Unidos) | Highest (~4.5M) |
|  | France (Francia) | ~3.5M |
|  | Mexico (México) | ~3M |

### 5.  Category Profitability

| Most Profitable | Least Profitable |
|---|---|
|  Fishing (₹7,56,221) | Strength Training (₹332) |
|  Cleats (₹4,94,637) | CDs (₹384) |
|  Camping & Hiking (₹4,27,456) | As Seen on TV! (₹714) |

> **Fishing category generates 2,000x more profit than Strength Training!** Clear indication of where to focus resources.

---

##  Python Analysis — Step by Step

### Phase 1 — Data Loading & Exploration
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv('DataCoSupplyChainDataset.csv', encoding='latin-1')
print(f"Rows: {df.shape[0]}, Columns: {df.shape[1]}")
df.head()
```

### Phase 2 — Delivery Status Distribution
```python
status_counts = df['Delivery Status'].value_counts()
plt.pie(status_counts, labels=status_counts.index, autopct='%1.1f%%')
plt.title('Delivery Status Distribution')
plt.show()
```

### Phase 3 — Shipping Mode vs Late Delivery
```python
shipping_delay = df.groupby('Shipping Mode')['Late_delivery_risk'].mean()
sns.barplot(x=shipping_delay.index, y=shipping_delay.values)
plt.title('Late Delivery Risk by Shipping Mode')
plt.show()
```

### Phase 4 — Category Profitability
```python
category_profit = df.groupby('Category Name')['Benefit per order'].sum().sort_values(ascending=False)
print(category_profit.head(10))
```

---

##  Power BI Interactive Dashboard

The project includes a fully interactive **Power BI Dashboard** with:

| Visual | Description |
|---|---|
|  KPI Card | Total Orders (180.519K) |
|  KPI Card | Average Late Delivery Risk (0.55) |
|  Bar Chart | Late Delivery % by Shipping Mode |
|  Bar Chart | Top 10 Profitable Categories |
|  Bar Chart | Top 10 Regions by Late Delivery |
| Slicer | Region-wise filter (interactive) |

###  Dashboard Features:
- **Cross-filtering** — Click any bar to filter all charts simultaneously
- **Hover tooltips** — Hover on any bar for detailed values
- **Region Slicer** — Filter entire dashboard by region in one click
- **Top N Filters** — Charts show only Top 10 for clean readability

>  Open `Supply_Chain_Dashboard.pbix` in Power BI Desktop to explore the interactive dashboard.

---

##  Recommendations

1. **Urgently review First Class shipping** — 95.3% late delivery for a premium service is unacceptable and likely causing customer churn.
2. **Treat late delivery as a systemic issue** — all regions are equally affected, so fix the core fulfillment process, not region-specific operations.
3. **Increase investment in Fishing, Cleats & Camping & Hiking** — these are top profit generators.
4. **Re-evaluate Strength Training, CDs & "As Seen on TV"** — extremely low profit contribution; consider pricing changes or phase-out.
5. **Prioritize US, France & Mexico markets** — they generate the highest sales and deserve premium service levels.

---

##  How to Run This Project

### Python Analysis
```bash
# 1. Clone this repository
git clone https://github.com/YOUR-USERNAME/supply-chain-analysis.git
cd supply-chain-analysis

# 2. Install required libraries
pip install pandas matplotlib seaborn

# 3. Open notebook in VS Code
# Open analysis.ipynb and Run All cells
```

### Power BI Dashboard
```
1. Download and install Power BI Desktop (free)
2. Open Supply_Chain_Dashboard.pbix
3. Explore the interactive dashboard!
```

---

##  Future Improvements

| Improvement | Description | Difficulty |
|---|---|---|
|  Late Delivery Prediction | ML model to predict delays before they happen | Intermediate |
|  Demand Forecasting | Time series model to forecast future orders | Advanced |
|  Supplier Scoring | Rate suppliers by performance metrics | Intermediate |
|  Web Dashboard | Deploy dashboard online using Streamlit | Intermediate |

---

##  Author

Built as a self-driven **Data Analyst Portfolio Project** to demonstrate end-to-end data analysis skills:
- Data cleaning & wrangling (Python/Pandas)
- Exploratory Data Analysis (Matplotlib/Seaborn)
- Business insight generation
- Interactive dashboard creation (Power BI)

---
