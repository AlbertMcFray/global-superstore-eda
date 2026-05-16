# Global Superstore — Exploratory Data Analysis

End-to-end EDA on the Global Superstore dataset covering data preparation, SQL analytics, RFM customer segmentation, and discount impact analysis.

---

## Project Structure

```
global-superstore-eda/
├── global_superstore_eda.ipynb   # Main analysis notebook
└── README.md
```

> **Dataset** — [Global Superstore](https://www.kaggle.com/datasets/shekpaul/global-superstore) (not included in the repo; download separately and place as `superstore.csv`).

---

## What's Inside

### Layer 0 — Data Preparation
- Dropped redundant columns (`Customer.Name`, row counter)
- Parsed date columns (`Order.Date`, `Ship.Date`) to datetime
- Renamed columns to snake_case for SQL compatibility
- Removed duplicates and handled nulls

### Layer 1 — SQL Analytics (SQLite in Python)
Four business questions answered with window functions and aggregations:

| # | Question |
|---|----------|
| 1 | Top 10 countries by revenue |
| 2 | Profitability by category and market |
| 3 | Which customer segment generates the most profit |
| 4 | Month-over-month sales trends (MoM growth %, running totals) |

Key findings: the US leads with $2.3M revenue; Technology dominates profit across APAC and developed markets; Consumer segment drives the most orders while Corporate has a higher average order value.

### Layer 2 — Python / Pandas
- **RFM Segmentation** — customers scored on Recency, Frequency, Monetary and grouped into Champions, Loyal, Potential Loyalist, At Risk, and Lost
- **Discount Analysis** — correlation between discount size and profitability
- **Visualisations** — bar charts for segment distribution, average revenue, and customer share (matplotlib / seaborn)

Key finding: Champions are only 10% of the customer base but generate ~4× the revenue per customer; the At Risk segment has spend comparable to Loyal customers and is the priority for retention.

---

## Stack

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| pandas | Data manipulation |
| numpy | Numerical operations |
| sqlite3 | In-memory SQL queries |
| matplotlib / seaborn | Visualisation |

---

## How to Run

```bash
git clone https://github.com/<your-username>/global-superstore-eda.git
cd global-superstore-eda

pip install pandas numpy matplotlib seaborn

# Place superstore.csv in the project root, then open the notebook
jupyter notebook global_superstore_eda.ipynb
```

---

## Author

[Your Name](https://github.com/your-username)
