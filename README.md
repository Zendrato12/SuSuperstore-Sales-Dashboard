# 📊 Superstore Sales Dashboard – Power BI Project

## 🎯 Project Overview
This project visualizes and analyzes sales performance from the fictional **Superstore** dataset using **Power BI**. It aims to extract business insights related to total sales, profitability, discount impact, and shipping performance across different regions and product categories.

---

## 📦 Dataset
- **Name**: `Sample - Superstore.csv`
- **Source**: [Kaggle Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- **Records**: ~10,000 transactions (2014–2017)
- **Fields**: Order Date, Sales, Profit, Discount, Region, Category, Product, Ship Mode, etc.

---

## 🛠️ Tools & Technologies
- Microsoft **Power BI Desktop**
- **Power Query Editor** (for cleaning & transformation)
- **DAX (Data Analysis Expressions)** for calculated measures
- CSV format dataset

---

## 🧩 Key Steps Performed

### 1. Data Preparation
- Removed irrelevant columns (`Row ID`, `Postal Code`)
- Created date breakdown: `Order Year`, `Order Month`, `Quarter`
- Calculated shipping efficiency with:  
  `Processing Days = Ship Date - Order Date`

### 2. DAX Measures
```dax
Profit Margin = DIVIDE(SUM(Superstore[Profit]), SUM(Superstore[Sales]), 0)

Total Discount = SUMX(Superstore, Superstore[Sales] * Superstore[Discount])

Avg Processing Days = AVERAGE(Superstore[Processing Days])
