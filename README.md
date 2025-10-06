# 🛒 E-Commerce Dataset – EDA Project

## 📌 Project Overview

This project explores and analyzes the E-Commerce Dataset (Kaggle) using Python.
The goal is to perform data cleaning, feature engineering, and exploratory data analysis (EDA) to uncover insights about sales trends, product performance, and customer behavior.

## 📂 Dataset Details

Source: Kaggle – E - Commerce Data (Link - https://www.kaggle.com/datasets/carrie1/ecommerce-data )

## Description:

The dataset contains transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based online retail company.

## Key Features:

InvoiceNo – Invoice number (unique ID for each transaction)

StockCode – Product/item code

Description – Product description

Quantity – Number of items purchased

InvoiceDate – Date and time of the transaction

UnitPrice – Price per unit (GBP)

CustomerID – Unique identifier for each customer

Country – Customer’s country

## ⚙️ Steps Performed

## 🔹 Data Cleaning

Checked for missing values (df.isnull().sum())

Removed duplicate records (df.drop_duplicates())

Dropped rows with missing CustomerID values

Identified and removed transactions with negative quantities or unit prices

## 🔹 Feature Engineering

Created a new feature:

Revenue = Quantity × UnitPrice

Extracted Year, Month, Day, and DayOfWeek from InvoiceDate

## 🔹 Identified skewness for each column based on the shape of the distribution

Distribution plots - <img width="1989" height="490" alt="image" src="https://github.com/user-attachments/assets/ff20f846-7e4b-4dc0-921d-2b078a5471b8" />

1️⃣ Quantity

Right-skewed, majority of transactions have small quantities, a few with very high quantities

2️⃣ UnitPrice

Right-skewed, most prices are low, few very expensive items

3️⃣ CustomerID

Right-skewed, few customers make many purchases, most make only a few

4️⃣ Revenue

Right-skewed, most revenues are low, few transactions generate very high revenue

✅ Summary: All numeric columns show positive (right) skewness, meaning long tail on the higher values.

## 🔹 Log Transformation to Reduce Skewness

To reduce the right skew in numeric columns, logarithmic transformation (log1p) was applied to Quantity, UnitPrice, CustomerID, and Revenue.

New columns were created with the _log suffix (e.g., Quantity_log)

Distributions after log transformation are closer to normal, making data more suitable for analysis and modeling

Plot after transformation - <img width="1489" height="390" alt="image" src="https://github.com/user-attachments/assets/ae3d8e1f-42b8-4ea8-9668-8f84155f102f" />

Used heatmap to show the correlation of numeric columns

## 🔹 Exploratory Data Analysis

Summary statistics with df.describe()

Revenue over time (line plot)

Monthly revenue trends (groupby Year, Month)

Boxplot of Quantity to detect outliers

Dot product check (Quantity × UnitPrice) for total revenue consistency

## 📊 Visualizations & Insights

📈 Revenue Over Time – A line plot showing how total revenue changes with time

<img width="876" height="470" alt="image" src="https://github.com/user-attachments/assets/d81b0486-399d-40c7-a7ac-18430df033ed" />

📅 Probability Distribution by Country - A pie chart showing top 5 country

<img width="711" height="581" alt="image" src="https://github.com/user-attachments/assets/50720445-227b-4c11-8102-4e293a329991" />

📦 Boxplot of Quantity - Highlighted extreme values and outliers in orders

<img width="558" height="374" alt="image" src="https://github.com/user-attachments/assets/e22ecf19-8d41-497f-814e-401695708ab3" />

💰 Revenue vs Quantity - A scatter plot showing correlation between revenue and quantity

<img width="597" height="455" alt="image" src="https://github.com/user-attachments/assets/08109e50-eec7-4564-8b4d-4e87e568cef0" />

🧾 Invoices Per Year – A pie chart showing total number of invoices issued each year

<img width="419" height="427" alt="image" src="https://github.com/user-attachments/assets/3b305f9a-5fc3-48c0-8c61-988590e9cfd5" />

🏆 Top 10 Products by Quantity Sold – Bar chart of the most purchased products

<img width="989" height="690" alt="image" src="https://github.com/user-attachments/assets/f7da429a-e96a-45ff-8248-de81dcde6630" />

## 📌 Tech Stack

Language: Python 🐍

Libraries: Pandas, NumPy, Matplotlib

## ✅ Results & Findings

Dataset had missing CustomerID values → cleaned.

Negative Quantity and UnitPrice indicated returns/cancellations → removed.

Seasonal patterns detected in monthly revenue.

Outliers in Quantity identified through boxplots.

Revenue feature successfully engineered for deeper analysis.

Analyzing Top Revenue Generating Items per Month - <img width="1191" height="590" alt="image" src="https://github.com/user-attachments/assets/40556b5b-9015-477f-b9a8-86de28b8e7d2" />
