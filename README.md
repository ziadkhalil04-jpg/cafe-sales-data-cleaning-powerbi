# ☕ Cafe Sales – Data Cleaning & Power BI Dashboard

Cleaning a messy 10,000-row cafe sales dataset with **Power Query**, then building an interactive **Power BI** dashboard with **DAX** measures on top of the clean data.

---

## 📌 Project Overview

Real-world data is rarely ready for analysis. This project starts from a raw cafe sales dataset full of missing values and invalid entries, cleans it step by step in Power Query, and turns it into a dashboard that answers basic business questions about sales performance.

## 🛠️ Tools

| Tool | Used for |
|---|---|
| **Power Query (M)** | Data cleaning and transformation |
| **DAX** | Measures and KPIs |
| **Power BI** | Data dashboard |

## 📂 Dataset

| Column | Description |
|---|---|
| Transaction ID | Unique ID per transaction |
| Item | Product sold (Coffee, Tea, Cake, Cookie, Salad, Sandwich, Smoothie, Juice) |
| Quantity | Units sold |
| Price Per Unit | Price of one unit |
| Total Spent | Quantity × Price Per Unit |
| Payment Method | Cash, Credit Card, Digital Wallet |
| Location | In-store or Takeaway |
| Transaction Date | Date of the transaction (2023) |

## 🧹 Data Quality: Before vs. After

| Metric | Before (Dirty) | After (Clean) |
|---|---|---|
| Rows | 10,000 | 3,511 |
| Columns | 8 | 8 |
| Problematic cells (Null / ERROR / UNKNOWN) | 10,082 (12.6% of all cells) | 0 in the core columns |
| Null values | 6,826 | 0 |
| "ERROR" values | 1,622 | 0 |
| "UNKNOWN" values | 1,634 | Only in categorical columns* |
| Rows with at least one issue | 6,911 (69.1%) | 0 |
| Invalid dates | 460 | 0 |
| Numeric columns stored as text | Yes | No |
| `Total Spent = Quantity × Price` | Not guaranteed | 100% consistent |

\* Remaining `UNKNOWN` values in the clean file: Item (55), Payment Method (134), Location (183).

### Most affected columns (dirty data)

| Column | Missing / invalid cells |
|---|---|
| Location | 3,961 |
| Payment Method | 3,178 |
| Item | 969 |
| Total Spent | 502 |
| Price Per Unit | 533 |
| Quantity | 479 |
| Transaction Date | 460 |

## 🔧 Cleaning Steps (Power Query)

> Replace this section with your actual Applied Steps.

1. Imported `dirty_cafe_sales.csv`
2. Promoted headers and checked data types
3. Replaced `ERROR` and `UNKNOWN` with `null` in numeric and date columns
4. Changed data types: Quantity → Whole Number, Price/Total → Decimal Number, Date → Date
5. Handled missing values (removed or filled, explain your choice here)
6. Removed the empty extra column
7. Validated that `Total Spent = Quantity × Price Per Unit`

## 📁 Repository Structure

```
cafe-sales-data-cleaning-powerbi/
├── README.md
├── data/
│   ├── raw/dirty_cafe_sales.csv
│   └── clean/cafe_sales_clean.csv
├── dashboard/
│   └── Cafe_Sales_Dashboard_Performance_BI.pbix
├── docs/
│   ├── dashboard.png
│   └── applied-steps.png
└── queries/
```

## 💡 Key Takeaways

- Nearly **7 out of 10 rows** in the raw data had at least one quality issue.
- Placeholder values like `ERROR` and `UNKNOWN` silently turn numeric columns into text, so they must be handled before any calculation.
- Validating business rules (e.g. `Total = Quantity × Price`) is a quick way to confirm the data can be trusted.

## 👤 Author

**Ziad ElSayed**, Business Information Systems graduate
🔗 [LinkedIn](www.linkedin.com/in/ziad-khalil-dev) ·
