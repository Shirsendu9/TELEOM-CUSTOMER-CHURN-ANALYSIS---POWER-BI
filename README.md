# Telecom Customer Churn Analysis - Power BI Project

## 📌 Overview

This Power BI project focuses on analyzing customer churn for a telecom company. The analysis provides insights into customer retention patterns, revenue loss, and high-risk customer segments. The project showcases crucial **DAX formulas**, KPI metrics, and interactive visualizations to aid business decision-making.

## 📊 Key Insights & Visuals

The dashboards contain:

- **Total Customers & Churned Customers** 📌

- **Churn Rate (%)** 📌

- **Revenue Lost due to Churn** 📌

- **Customer Churn by Contract Type** 📌

- **Churn Rate by Payment Method** 📌

- **High-Risk vs. Low-Risk Customers** 📌

- **Churn Rate by Internet Service** 📌

- **Tenure-based Customer Segmentation** 📌

- **Revenue Lost Due to Churn by Contract Period** 📌

- **Monthly Churn Prediction Insights** 📌

## 🛠️ DAX Cheat Sheet

Below are the key DAX formulas used in this project:

### **1. Total Customers**

```DAX

Total Customers = COUNT('Customer Data'[CustomerID])
```

### **2. Churned Customers**

```DAX

Churned Customers = CALCULATE([Total Customers], 'Customer Data'[Churn] = TRUE())
```

### **3. Churn Rate**

```DAX

Churn Rate = DIVIDE([Churned Customers], [Total Customers], 0)
```

### **4. Revenue Lost Due to Churn**

```DAX

Revenue Lost = SUMX(FILTER('Customer Data', 'Customer Data'[Churn] = TRUE()), 'Customer Data'[MonthlyCharges] * 'Customer Data'[Tenure])
```

### **5. High-Risk Customers**

```DAX

High Risk Customers = CALCULATE([Total Customers], 'Customer Data'[Contract] = "Month-to-month", 'Customer Data'[Churn] = TRUE())
```

### **6. Customer Segmentation by Tenure**

```DAX

Tenure Group =
    SWITCH(
        TRUE(),
        'Customer Data'[Tenure] <= 6, "0-6 months",
        'Customer Data'[Tenure] <= 12, "6-12 months",
        'Customer Data'[Tenure] <= 24, "1-2 years",
        'Customer Data'[Tenure] <= 36, "2-3 years",
        'Customer Data'[Tenure] <= 48, "3-4 years",
        'Customer Data'[Tenure] <= 60, "4-5 years",
        "5+ years"
    )
```

## 📁 Files in this Repository

- `Customer Churn Analysis.pbix` (Power BI file with all visuals and DAX formulas)

- `DAX_Cheat_Sheet.pdf` (Quick reference for DAX formulas used in the project)

- `Telecom Churn Dataset.csv` (Cleaned dataset used for the analysis)

- `README.md` (This document)

## 🚀 How to Use

1. **Download the Power BI file (`.pbix`)** 📥

2. Open in **Power BI Desktop** 📊

3. Explore the **dashboards & interactive visuals** 🔍

4. Review the **DAX formulas** and modify them if needed ⚙️

## 🔥 Key Takeaways

- The highest churn rate is among **Month-to-month** contract customers 📉

- Customers using **Electronic Check** as a payment method have the highest churn 🔍

- **Fiber optic users** have the highest churn rate among internet service types ⚡

- Revenue loss is significant for short-tenure customers 📊

---

⭐ **If you found this project useful, consider giving it a star on GitHub!** ⭐

---- 
Shirsendu Ghosh

Data Analyst

Mail: shirsendughosh9@gmail.com

