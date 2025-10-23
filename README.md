# E-commerce Sales Analysis & Prediction

This project focuses on analyzing and predicting e-commerce sales using data cleaning, preprocessing, and machine learning (Random Forest Regressor). The dataset contains customer transactions, order details, and product information. The goal was to understand key sales patterns and predict total revenue based on product and order features.

📊 Project Workflow
#1. Data Cleaning & Preprocessing

Removed rows with missing or invalid values in essential columns (price, grand_total, etc.).
Handled missing prices using SKU-wise median imputation.
Capped extreme percentile values (1st and 99th) to reduce the effect of outliers.
Converted numeric columns to optimal data types to save memory (e.g., float32, int8).
Extracted order_date and order_month from created_at.
Created derived features:
AOV (Average Order Value) = grand_total / qty_ordered
has_commission (flag column) for commission availability

#2. Feature Engineering:
Encoded categorical variables using LabelEncoder.
Scaled numerical columns (price, grand_total) using StandardScaler.
Aggregated customer-level data:
last_order (most recent order date)
orders (number of unique orders)
total_spend (total amount spent)
avg_order_value (average order size)
recency_days (days since last purchase)

3. Visualization:
Monthly sales trends were plotted to observe revenue fluctuations over time.
Y-axis represented total monthly sales (in scientific format like 1e8 = 100,000,000).

4. Modeling
Model Used: Random Forest Regressor
Target Variable: grand_total

Features Used:
price
qty_ordered
discount_amount
Data Split: 80% training and 20% testing

5. Model Evaluation
Metric	Score
R² Score	0.9726
MAE (Mean Absolute Error)	2186.90

✅ Interpretation:
The model explains about 97.26% of the variance in total sales (grand_total), with an average prediction error of around Rs. 2186, which indicates strong model accuracy and reliable predictions.

6. Files Saved:
ecom_cleaned.parquet – Full cleaned dataset
ecom_sample.parquet – 100K row sample for quick testing

⚙️ Technologies Used:
Python
Pandas
NumPy
Matplotlib
Scikit-learn

📁 Project Structure
📦 Ecom-Sales-Analysis
 ┣ 📜 ecom_cleaned.parquet
 ┣ 📜 ecom_sample.parquet
 ┣ 📜 README.md
 ┣ 📜 ecom_analysis.ipynb
 ┗ 📊 graphs/

💡 Key Insights

Seasonal spikes in monthly revenue were observed around late 2017.
Outlier handling significantly improved model accuracy.
Strong correlation between price and total order value.
