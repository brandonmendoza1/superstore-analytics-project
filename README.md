# Superstore Analytics Project
This repository contains an end-to-end analytics workflow performed on the **Superstore** dataset using Excel, Power Query, Tableau, and statistical modeling techniques.

The project demonstrates skills in:
- Data cleaning & preparation
- Exploratory data analysis
- Regression modeling
- Shipping performance evaluation
- Customer/segment profitability analysis
- Dashboard planning
- Predictive modeling foundations

---

## 📊 1. Regression Analysis (Profit Prediction)

**Objective:**  
Identify whether *Sales*, *Quantity*, *Discount*, and *Shipping Mode* predict **Profit**.

### Work Completed:
- Built a multiple regression model in Excel.
- Verified assumptions using:
  - Scatterplots  
  - Residual analysis  
  - Multicollinearity checks  
- Identified statistically significant predictors.
- Exported all regression outputs and charts.

### Key Insights:
- **Discount** had the strongest negative effect on profit.
- **Sales** positively predicted profit, but with diminishing returns.
- Shipping mode showed minimal direct effect when controlling for other variables.

---

## 🚚 2. Shipping Mode Analysis

**Objective:**  
Determine whether certain shipping modes are associated with higher/lower profitability.

### Work Completed:
- Created bar charts of:
  - Average sales per ship mode  
  - Average profit per ship mode  
  - Count of orders per ship mode  
- Explored relationship between shipping mode and return rates (if applicable).

### Key Insights:
- Standard Class was the most frequently used but not the most profitable.
- Second Class and First Class had higher per-order profitability.

---

## 👥 3. Customer Profitability & Segmentation Analysis

**Objective:**  
Understand which customer groups drive business results.

### Work Completed:
- Created pivot tables summarizing:
  - Profit per customer
  - Sales per customer
  - Profitability by customer segment
- Built highlight tables and rankings.
- Prepared data for later clustering (k-means).

### Key Insights:
- Corporate segment generated the highest total profit.
- Home Office segment had lower volume but higher profit margins.
- Some customers were consistently unprofitable — potential targets for discount policy changes.

---

## 📦 4. Product-Level Performance

**Objective:**  
Evaluate which product categories/subcategories drive results.

### Work Completed:
- Category and Sub-Category performance analysis
- Product-level Pareto (80/20) analysis
- Profitability and return risk comparison

---

## 🧠 5. Preparation for Predictive Modeling (K-Means, CART)

Though K-means and decision trees were not executed in Excel, prep work was completed:
- Cleaned customer-level dataset
- Engineered fields for clustering:
  - Total Sales
  - Total Orders
  - Total Profit
  - Average Discount
  - Segment/Region indicators

---

## 📈 6. Dashboard Planning (Next Steps in Tableau/PowerBI)

Dashboard ideas implemented or prepared:
- Customer Profitability Dashboard
- Segment Performance Dashboard
- Product Mix Dashboard
- Shipping Mode Overview
- Profit Drivers from Regression

---

## 🛠 Tools Used

- **Excel** (primary analytics, regression, charts)
- Power Query (data transformation)
- Tableau / Power BI (visualization & modeling)
- GitHub (version control & portfolio)

---

## 📘 Summary

This project showcases Excel-based business analytics with a full workflow:
1. Cleaning data  
2. Modeling  
3. Visualization  
4. Business insight generation  

It demonstrates strong analytical reasoning, statistical modeling fundamentals, and business intelligence preparation.

---

If you'd like to see the dashboard visuals or run future machine learning models (k-means, CART), feel free to explore the Tableau or future notebooks.

