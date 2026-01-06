# Superstore Analytics Project
## 📌 Project Overview
This self-initiated project explores which operational factors are associated with order fulfillment delays using the Superstore dataset. The goal was to identify meaningful drivers of fulfillment performance and translate those findings into clear, decision-oriented insights.

Using Excel, Power Query, and regression analysis, I integrated multiple data sources, engineered an order-level performance metric, and evaluated the statistical relevance of customer, geographic, and operational variables. The analysis ultimately identified **shipping method** as the primary factor associated with fulfillment delay.
![Excel Dashboard Overview](images/dashboard_overview.png)
This project demonstrates an end-to-end analytical workflow, from raw data preparation to modeling and visualization. After transforming line-item order data into an order-level dataset, I applied multiple linear regression to assess which variables were meaningfully associated with fulfillment delay.

While customer segment, geographic region, and order characteristics were evaluated, shipping mode emerged as the most relevant operational lever. These findings were validated using pivot-based exploratory analysis and a dynamic Excel dashboard designed to communicate results clearly.

- **Microsoft Excel**
  - Power Query for data integration and transformation
  - Pivot Tables for exploratory analysis
  - Regression Analysis ToolPak for statistical modeling
  - Dashboards and charts for visualization
- **Analytical Techniques**
  - Data cleaning and table synchronization
  - Feature engineering (OrderLagDays)
  - Dummy variable encoding
  - Multiple linear regression

### 🧠 **Key Objectives**
- Combine customer and order data into a unified analytical dataset
- Use regression analysis to examine relationships between variables
- Engineer a new variable measuring fulfillment speed
- Build a dashboard to communicate insights clearly
### 📂 **Data Source**
The project uses two primary tables from the Superstore Dataset:
- Customers: customer demographics and segment information
- Orders: order details including order date and ship date

Excel File: [Superstore Dataset](superstore_dataset.xlsx)

Alternatively, the Excel file `superstore_dataset.xlsx` can be accessed within this repository above.

---

### 🔧 Data Preparation & Transformation
Power Query was used to integrate and transform the raw Superstore data into a modeling-ready dataset.

The original orders data was recorded at the **line-item level**, with multiple rows per order due to multiple products per purchase. Because fulfillment delay is an **order-level outcome**, the data was aggregated to one row per order by grouping on Order ID and computing order-level metrics such as total quantity, discount usage, and average discount percent.

I engineered the target variable **OrderLagDays** as the difference between Ship Date and Order Date. Customer attributes (segment and geographic information) were then merged into the order-level table via Customer ID using a left join. The resulting dataset served as the foundation for exploratory analysis, regression modeling, and dashboard visualization.
![Order-Level Aggregration in Power Query](images/custom_groupby.png)
![OrderLagDays Feature Engineering](images/orderlagdays_column.png)

## 📈 Regression Analysis
To formally evaluate drivers of fulfillment delay, I constructed a multiple linear regression model with **OrderLagDays** as the dependent variable.

Categorical variables (including shipping mode, customer segment, and region) were converted into dummy variables to allow structured comparison across categories while holding other factors constant. The regression was run using Excel’s Analysis ToolPak, and model outputs were evaluated based on coefficient direction, statistical significance, and overall model fit.

This model was used as an **exploratory tool** to identify which variables were meaningfully associated with fulfillment delay rather than as a purely predictive model.
![Regression Analysis Output](images/regression_analysis.png)

## 💡 Key Insights
- **Shipping mode is the primary variable associated with fulfillment delay** in this model. Same Day, First Class, and Second Class shipping options are all statistically significant and are associated with fewer **OrderLagDays** relative to the baseline shipping method (Standard Class).
- **Customer segment variables** (Consumer, Corporate, Home Office) are not statistically significant, suggesting that customer type does not meaningfully explain variation in fulfillment speed once shipping method is accounted for.
- **Geographic variables** (East, West, South) are also not statistically significant, indicating that regional differences do not appear to drive fulfillment delays in this dataset.
- **Order-level characteristics**, including quantity, discount usage, and holiday timing, do not show significant relationships with fulfillment delay when controlling for shipping method.
- Overall, the results suggest that **fulfillment performance is driven more by operational decisions than by customer demographics or order attributes**.

---

## 📦 Shipping Mode Analysis

Because shipping mode emerged as the only statistically significant driver of fulfillment delay in the regression model, I examined it more closely using both the model coefficients and descriptive statistics.

Using **Standard Class** as the baseline category, the regression results indicate:
- **Same Day** shipping is associated with an average reduction of approximately **2.63 days**
- **First Class** shipping is associated with an average reduction of approximately **2.27 days**
- **Second Class** shipping is associated with an average reduction of approximately **1.38 days**

These results are consistent with the summary statistics shown in the dashboard: average order lag decreases monotonically as shipping speed increases, with Standard Class exhibiting the highest average lag and Same Day the lowest.

Together, the regression and descriptive analysis reinforce the conclusion that **fulfillment performance in this dataset is driven primarily by operational shipping choices rather than customer demographics, geography, or order attributes**.
![Average Lag by Shipping Mode](images/avg_lag_shipping_mode.png)

---

## 📊 Dashboard & Visualization
An Excel dashboard was created to support exploratory analysis and visually reinforce findings from the regression model.

### Top Ordering Cities (Including Segments)
![Top Ordering Cities by Segment](images/top_ordering_cities.png)
A stacked bar chart displays the number of orders by city, segmented by customer type (Consumer, Corporate, Home Office). This visualization highlights:
- Cities with the highest order volume (e.g., Los Angeles, New York City, Philadelphia)
- The distribution of customer segments within high-volume cities
- How order activity is concentrated geographically while customer mix remains relatively balanced

This chart provides business context around where orders originate, while supporting the regression finding that customer segment itself is not a primary driver of fulfillment delay.

### Average Fulfillment Lag by Shipping Mode
The dashboard includes a bar chart comparing average **OrderLagDays** across shipping methods. The visualization shows a clear monotonic pattern, with Same Day shipments having the lowest average lag and Standard Class the highest.

This view provides a quick, visual summary of fulfillment performance by shipping method and complements the regression-based analysis discussed above.

---

## ⚠️ Limitations & Next Steps
- The regression model explains a moderate portion of the variation in fulfillment delay (R² ≈ 0.35) and is intended for exploratory insight rather than precise prediction.
- Additional features such as product category, seasonal effects, or carrier-level data could further improve explanatory power.
- Future analysis could explore non-linear models or validation on a larger dataset.

---

## 🧾 Summary

This project demonstrates a full analytical workflow using the Superstore dataset, from raw data integration and feature engineering to regression analysis and dashboard creation. By transforming line-item data into an order-level dataset and evaluating key predictors of fulfillment delay, the analysis found that **shipping mode** is the most meaningful operational driver of fulfillment performance. The project highlights practical Excel analytics skills and delivers insights relevant to business operations and decision-making.

---
