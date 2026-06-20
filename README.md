#  Supply Chain Optimization Analysis

A data analysis project exploring supply chain performance using the **DataCo Smart Supply Chain Dataset**. The analysis identifies delivery bottlenecks, evaluates shipping mode reliability, and highlights profit/loss patterns across product categories.

---

##  Objective

Analyze end-to-end supply chain data to:
- Identify the rate and causes of late deliveries
- Compare shipping mode reliability
- Understand regional delivery performance
- Evaluate profitability across product categories
- Provide data-backed recommendations for operational improvement

---

##  Dataset

**Source:** [DataCo Smart Supply Chain Dataset (Kaggle)](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain)

- **Rows:** 180,519
- **Columns:** 53 (14 used for focused analysis)
- Contains order details, shipping modes, delivery status, regional data, sales, and profit/loss per order.

---

##  Tools & Libraries

- **Python 3.13**
- **Pandas** – data cleaning & manipulation
- **Matplotlib** & **Seaborn** – data visualization
- **Jupyter Notebook** (via VS Code)

---

##  Key Insights

### 1. Late Deliveries Are a Major Issue
**54.8%** of all orders were delivered late — more than half the total order volume.

### 2. Shipping Mode Reliability (Late Delivery Rate)
| Shipping Mode | Late Delivery Rate |
|---|---|
| First Class | 95.3% |
| Second Class | 76.6% |
| Same Day | 45.7% |
| Standard Class | 38.1% |

> Counter-intuitively, **First Class** — the premium, fastest shipping option — has the **highest** late delivery rate of all modes, indicating a major service reliability gap for customers paying for priority shipping.

### 3. Late Delivery Is a Global, Systemic Issue
Late delivery rates across all regions fall between **48% and 58%**, showing the problem is not isolated to a specific region but is company-wide.

| Top Affected Regions | Late Delivery Rate |
|---|---|
| Central Africa | 57.9% |
| South Asia | 56.3% |
| East Africa | 55.9% |

### 4. Top Sales-Generating Countries
The **United States**, **France**, and **Mexico** are the top three countries by total sales, with the U.S. market significantly outperforming others.

### 5. Category Profitability
| Most Profitable Categories | Least Profitable Categories |
|---|---|
| Fishing | Strength Training |
| Cleats | CDs |
| Camping & Hiking | As Seen on TV! |
| Cardio Equipment | Books |
| Women's Apparel | Toys |

> The **Fishing** category generated over **750,000** in total benefit — more than 2,000x the lowest-performing category (Strength Training).

---

##  Recommendations

1. **Investigate First Class shipping operations** — a 95% late delivery rate for a premium service likely damages customer trust and warrants immediate review of carrier/logistics partners.
2. **Address late delivery as a company-wide process issue**, not a regional one — since all regions show similarly high delay rates, the root cause is likely in scheduling or fulfillment processes rather than location-specific logistics.
3. **Reallocate inventory and marketing focus** toward high-margin categories like Fishing, Cleats, and Camping & Hiking.
4. **Reassess low-performing categories** (Strength Training, CDs, Books) for pricing, sourcing cost, or potential phase-out.

---

##  Project Structure

```
supply-chain-analysis/
│
├── analysis.ipynb                  # Main analysis notebook
├── DataCoSupplyChainDataset.csv    # Raw dataset
├── clean_supply_chain.csv          # Cleaned dataset (14 key columns)
└── README.md                       # Project documentation
```

---

##  How to Run This Project

1. Clone this repository
   ```bash
   git clone https://github.com/YOUR-USERNAME/supply-chain-analysis.git
   cd supply-chain-analysis
   ```
2. Install required libraries
   ```bash
   pip install pandas matplotlib seaborn
   ```
3. Open `analysis.ipynb` in VS Code or Jupyter Notebook and run all cells.

---

##  Future Improvements

- Build an interactive Power BI / Tableau dashboard
- Add predictive modeling for late delivery risk (classification model)
- Perform demand forecasting using time series analysis
- Conduct supplier-level performance scoring

---

##  Author

Created as part of a self-driven Data Analyst portfolio project.
