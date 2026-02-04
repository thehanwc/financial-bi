# financial-bi
A Financial Business Intelligence EDA &amp; Dashboard

Interactive Power BI dashboard and exploratory data analysis (EDA) for the **Power BI Financial Sample** dataset.

This repo contains:
- A **Power BI template dashboard** (`.pbit`) for executive and drill-through reporting
- An **exported PDF** preview of the dashboard pages
- The **source dataset** (`.csv`)
- A **Python notebook** for data cleaning, validation, and quick analysis

---

## Repository Structure

```text
.
├── financial_sample.csv            # Source dataset (Power BI Financial Sample)
├── financial_eda.ipynb             # Python EDA + cleaning + validation
├── financial_dashboard.pbit        # Power BI template (connect it to the CSV)
└── financial_dashboard.pdf         # Dashboard export (preview)
```

---

## Dashboard Preview (PDF)

The exported dashboard includes:
- **Executive Overview** (headline KPIs + trends + top segments/products/countries)
- **Sales Performance** (sales by product/segment/month)
- **Profitability Analysis** (profit by product/segment + margin)
- **Geographic Performance** (sales/profit/units by country + map)
- **Discount Impact** (sales vs profit by discount band + margin impact)
- **Detailed Drill-Through** (transaction-like table for slicing & investigation)

Key headline KPIs shown in the dashboard export:
- **Total Sales:** 118.73M  
- **Total Cost (COGS):** 101.83M  
- **Profit:** 16.89M  
- **Units Sold:** 1.13M  

---

## Key Findings (from this build)

### By Segment
- **Government** drives the largest sales (~52.5M) and profit (~11.39M).
- **Enterprise** is a risk area: it is the only segment showing **negative profit** in the profitability view.

### Top Products (Profit)
- **Paseo** is the top profit contributor (~4.8M), followed by **VTT** (~3.0M) and **Amarilla** (~2.8M).

### Geography
- Profit is led by **France** (~3.8M) and **Germany** (~3.7M).

### Discounting
- Higher discount bands reduce profitability materially (margin drops to ~9% at “High” discount), while “None” shows the strongest margin (~21.86%).

---

## Getting Started

### 1) Open the Power BI Dashboard (`.pbit`)
**Prerequisite:** Power BI Desktop (Windows)

1. Download / clone this repo
2. Open `financial_dashboard.pbit` in Power BI Desktop
3. When prompted for the data source, point it to:
   `financial_sample.csv`
4. Apply changes / refresh to load the dataset

### 2) Run the Python EDA Notebook
**Prerequisite:** Python 3.9+ (recommended)

Open:
- `financial_eda.ipynb`

If the notebook references a different filename (e.g., `Financial Sample.csv`), either:
- rename `financial_sample.csv`, or
- update the notebook path accordingly.

---

## Dataset Columns (Quick Data Dictionary)

Common business fields included:
- **Dimensions:** `Segment`, `Country`, `Product`, `Discount Band`, `Year`, `Month Name`, `Month Number`, `Date`
- **Measures:** `Units Sold`, `Manufacturing Price`, `Sale Price`, `Gross Sales`, `Discounts`, `Sales`, `COGS`, `Profit`

Typical metric relationships validated in EDA:
- `Sales = Gross Sales - Discounts`
- `Profit = Sales - COGS`

---

## What the EDA Notebook Does

The notebook (`financial_eda.ipynb`) is structured as a practical pipeline:
1. Load & inspect the dataset
2. Standardize column names
3. Clean data types (dates + numeric currency fields)
4. Check missing values & duplicates
5. Validate business-rule consistency (Sales/Profit equations)
6. Outlier detection (IQR)
7. Visualization (distributions + correlations)

---

## Notes

- This project uses the **Power BI Financial Sample** dataset (commonly used for learning analytics and dashboard design).
- The PDF is an export of the Power BI report; the `.pbit` is the interactive template version.
