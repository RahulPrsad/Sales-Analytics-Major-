# Advanced Sales Analytics using PySpark

This project performs **advanced analytics on retail transaction data** using Apache Spark and PySpark.  
It focuses on extracting meaningful business insights from cleaned data.

---

# Project Overview

After building a basic ETL pipeline, this project dives deeper into the dataset to answer key business questions:

- Who are the top customers?
- Which products sell the most?
- What are the monthly revenue trends?
- Which countries generate the highest revenue?

This project demonstrates how raw data can be transformed into **actionable insights**.

---

# 🛠 Technologies Used

- Apache Spark
- PySpark
- Python
- Databricks / Jupyter Notebook
- Parquet (for optimized storage)

---

# Dataset

The project uses the **Online Retail Dataset**, which contains transactional data of an online store.

### Key Columns

| Column | Description |
|------|-------------|
| InvoiceNo | Transaction ID |
| StockCode | Product code |
| Description | Product name |
| Quantity | Items purchased |
| InvoiceDate | Date of transaction |
| UnitPrice | Price per item |
| CustomerID | Customer identifier |
| Country | Customer location |

---

# Data Processing Steps

## 1️⃣ Data Cleaning

- Removed null values
- Filtered negative quantities (returns)
- Converted InvoiceDate to timestamp

---

## 2️⃣ Feature Engineering

Created a new column:


## 3️⃣ Time Feature Extraction
Extracted month from InvoiceDate for time-based analysis.

---

# 📈 Business Insights

## 1️⃣ Top Customers

```python
df.groupBy("CustomerID") \
.agg(sum("Revenue").alias("TotalSpent")) \
.orderBy("TotalSpent", ascending=False)


