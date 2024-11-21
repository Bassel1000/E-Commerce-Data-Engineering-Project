# Transforming E-Commerce Data into Actionable Insights

## Overview
This project aims to develop a data engineering and analytics pipeline to process e-commerce transaction data, generate actionable insights, and optimize business decisions. It integrates **Microsoft Azure** tools and **machine learning** techniques to deliver a seamless, data-driven solution.

## Key Objectives
- Automate data ingestion, transformation, and storage using **Azure Data Factory**.
- Clean and preprocess datasets for accurate analysis.
- Perform advanced SQL querying and exploratory data analysis.
- Visualize insights using **Power BI** dashboards.
- Apply machine learning to predict sales trends.

## Datasets Overview
The analysis used four datasets:
1. **Customers Table:** Customer demographics and segmentation.
2. **Invoices Table:** Transaction records with timestamps.
3. **InvoiceItems Table:** Product details per transaction.
4. **Products Table:** Product descriptions and pricing.

---

## Data Engineering Process

### Data Cleaning
Key cleaning steps for ensuring dataset quality:
- **Customers Table:** Removed missing values and converted `CustomerID` to string.
- **Invoices Table:** Fixed `InvoiceDate` to datetime format.
- **InvoiceItems Table:** Removed negative quantities and recalculated `TotalPrice`.
- **Products Table:** Removed invalid stock codes.

### Infrastructure Setup
Utilized the following Azure resources:
1. **Azure Storage Account:** Hosted the raw CSV datasets.
2. **Azure SQL Server & Database:** Stored cleaned and transformed data.
3. **Azure Data Factory:** Automated data flow from ingestion to SQL storage.

### Azure Data Factory Pipeline
- Designed separate data flows for each dataset.
- Orchestrated pipeline ensured sequential loading of datasets into SQL tables.

---

## SQL Querying and Analysis
Created a unified table (`SalesSummary`) to streamline analysis:
- **Sales per Customer:** Aggregated total sales by customer.
- **Top-Selling Products:** Identified most purchased items.
- **Sales Trends:** Analyzed invoices over specific timeframes.

Sample Query:
```sql
SELECT StockCode, Description, SUM(Quantity) AS TotalQuantitySold
FROM SalesSummary
GROUP BY StockCode, Description
ORDER BY TotalQuantitySold DESC;
```
## Exploratory Data Analysis (EDA)

We conducted EDA to uncover patterns and trends in customer behavior, product performance, and sales. These insights are crucial for strategic decision-making in marketing, inventory management, and product development.

### Key Insights
1. **Market Analysis:**  
   - The UK dominates sales, accounting for 89% of transactions.  
   - Other European markets like Germany and France show growth potential.

2. **Product Performance:**  
   - The product "PAPER CRAFT, LITTLE BIRDIE" is the top-seller, reflecting high customer demand for event and party supplies.  
   - Other high-performing categories suggest opportunities for themed promotions and inventory optimization.

3. **Sales Trends:**  
   - Sales peak in November, likely due to holiday shopping, with steady growth observed throughout the year.  
   - Analysis of non-peak periods can help optimize marketing strategies.

4. **Pricing Insights:**  
   - Most transactions involve lower-priced items. This suggests opportunities for upselling, bundling, or promotions targeting higher-value products.

---

## Machine Learning

We applied machine learning to predict sales trends and enhance decision-making capabilities. Key tools and techniques include:

### Libraries Used
- **NumPy**: Numerical computations.  
- **Pandas**: Data manipulation.  
- **Scikit-learn**: Machine learning model training and evaluation.

### Workflow
1. **Data Loading:** Loaded the cleaned datasets.  
2. **Data Splitting:** Divided the data into training and testing sets using `train_test_split`.  
3. **Feature Scaling:** Standardized features with `StandardScaler`.  
4. **Model Training:** Trained a Support Vector Classifier (SVC).  
5. **Evaluation:** Measured model performance using accuracy scores.

---

## Key Outcomes and Business Impact

### Data-Driven Insights
- **Market Focus:** The UK is the primary market, warranting targeted campaigns and investments.
- **Inventory Management:** Insights into top-selling products enable better stock planning.
- **Sales Optimization:** Analysis of sales trends and pricing supports revenue growth strategies.

### Dashboards
- Built interactive dashboards using **Power BI** to present:
  - Customer demographics.
  - Sales trends and forecasts.
  - Product performance metrics.

### Thank You
Feel free to explore this repository.
