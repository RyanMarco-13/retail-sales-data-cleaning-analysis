# Retail Sales Data Cleaning & Dashboard Analysis

## 📌 Problem Statement
Raw retail sales dataset (12,575 transactions) with real-world data quality 
issues — missing values in Item, Price Per Unit, Quantity, Total Spent, and 
Discount Applied columns. Goal: clean the data using Excel formulas and build 
an interactive dashboard to surface business insights.

Dataset source: [Kaggle - Dirty Retail Store Sales](https://www.kaggle.com/datasets/ahmedmohamed2003/retail-store-sales-dirty-for-data-cleaning)

## 🧹 Data Cleaning Process
1. **Item column** — blank values filled with "Unknown Item"
2. **Price/Quantity/Total** — these three fields are mathematically related 
   (Total = Price × Quantity). Used formulas to recover missing values where 
   possible (e.g., Price = Total ÷ Quantity). Where **both Quantity and Total 
   were missing simultaneously (604 rows)**, the value could not be 
   mathematically recovered — these were flagged rather than guessed, to 
   avoid introducing bias into the analysis.
3. **Discount Applied** — blank values labeled "Not Recorded" instead of 
   assuming "No", since assuming would skew the discount impact analysis.
4. Added a **Data Quality Flag** column to track which rows had recoverable 
   vs. unrecoverable issues.

## 📊 Analysis & Dashboard
Built using PivotTables + charts:
- Revenue by Category
- Revenue by Location (Online vs In-store)
- Revenue by Payment Method
- Month-wise Revenue Trend
- Discount Applied Impact on Average Order Value
- Top 10 Highest Spending Customers

![Dashboard](Sales%20data%20Dashboard.jpg)

## 🔍 Key Insights
- **[Category]** generated the highest revenue among all 8 categories.
- Online vs In-store revenue split was nearly balanced (~50/50).
- Discount had **minimal impact** on average order value (₹130.49 with 
  discount vs ₹129.95 without) — suggesting current discounting may not be 
  effectively driving larger purchases.
- January showed a significant revenue spike compared to other months.

## 🛠️ Tools Used
Excel (Formulas: IF, ISBLANK, SUMIFS, COUNTIFS, INDEX-MATCH), PivotTables, 
PivotCharts, Slicers

## 📁 Files
- `raw_sales_data.csv` — original unprocessed data
- `retail_sales_project.xlsx` — full workbook (Raw + Cleaned + Summary + Dashboard sheets)
- `dashboard_screenshot.png` — dashboard preview
