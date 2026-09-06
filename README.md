Online Retail Data Analysis
E-Commerce Sales Performance and Customer Insights

This project presents a complete data analysis of an Online Retail transactional dataset using Python. The analysis focuses on data cleaning, exploratory data analysis (EDA), outlier treatment, data visualization, and business insights.

The objective is to understand sales performance, identify top-performing products and markets, analyze customer behavior, and provide data-driven recommendations.

📊 Dataset

The dataset used in this project is the Online Retail Dataset, containing transactional records from a UK-based online retail store.

Dataset Overview
Original Records: 541,909
Features: 8
Time Period: December 2010 – December 2011
Countries: 38
Unique Products: 3,925
Unique Customers: 4,339
Final Cleaned Sales Records: 525,460
Features
Column	Description
InvoiceNo	Unique transaction/invoice number
StockCode	Product identification code
Description	Product description
Quantity	Number of items purchased
InvoiceDate	Date and time of transaction
UnitPrice	Price per item
CustomerID	Unique customer identification number
Country	Customer's country
🛠️ Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
OpenPyXL
Jupyter Notebook
PyCharm
🧹 Data Cleaning

The following data-cleaning techniques were applied:

Converted InvoiceDate into datetime format.
Removed duplicate records.
Removed records with missing product descriptions.
Identified and analyzed missing values.
Retained missing CustomerID records for overall sales analysis.
Identified cancelled transactions and negative quantities.
Removed negative-quantity transactions from sales analysis.
Removed negative UnitPrice records.
Retained zero-price transactions.
Detected outliers using the IQR (Interquartile Range) method.
Applied IQR capping to Quantity and UnitPrice.
Calculated Revenue using:
Revenue = Quantity × UnitPrice
📈 Exploratory Data Analysis

The project analyzes:

Sales Performance
Total revenue
Total quantity sold
Average revenue per transaction
Average unit price
Monthly Sales
Monthly revenue trends
Highest and lowest revenue months
Product Analysis
Top 10 products by revenue
Top 10 products by quantity
Country Analysis
Revenue by country
Highest-revenue country
Customer Analysis
Top customers by revenue
Average revenue per customer
Correlation Analysis

Relationships between:

Quantity and Revenue
UnitPrice and Revenue
Quantity and UnitPrice
Anomaly Analysis
Highest-revenue transactions
Highest-quantity transactions
📊 Visualizations

Five major visualizations were created:

1. Top 10 Products by Revenue

A bar chart showing the products generating the highest revenue.

2. Monthly Revenue Trend

A line chart showing changes in revenue over time.

3. Revenue Distribution

A histogram showing the distribution of revenue across transactions.

4. Correlation Heatmap

A heatmap showing relationships between Quantity, UnitPrice, and Revenue.

5. Quantity vs Revenue

A scatter plot showing the relationship between quantity sold and revenue.

🔍 Key Findings

Some of the major findings from the analysis are:

The United Kingdom was the dominant revenue-generating market.
November 2011 recorded the highest monthly revenue.
REGENCY CAKESTAND 3 TIER was the highest-revenue product.
JUMBO BAG RED RETROSPOT had the highest sales quantity.
Quantity had the strongest positive relationship with Revenue, with a correlation of approximately 0.523.
Revenue was concentrated among a relatively small number of high-value customers.
Quantity and UnitPrice had a moderate negative correlation of approximately -0.376.
💡 Business Recommendations

Project Summary

This project demonstrates how Python-based data analytics can be used to transform raw retail transaction data into meaningful business insights. The analysis provides an understanding of sales trends, product performance, customer value, geographical markets, and relationships between important sales variables.
