# E-commerce Sales Analysis & Prediction

This project focuses on analyzing and predicting e-commerce sales using data cleaning, preprocessing, and machine learning (Random Forest Regressor). The dataset contains customer transactions, order details, and product information. The goal was to understand key sales patterns and predict total revenue based on product and order features.

📊 Project Workflow
# 1. Data Cleaning & Preprocessing
Removed rows with missing or invalid values in essential columns (price, grand_total, etc.).<br>
Handled missing prices using SKU-wise median imputation.<br>
Capped extreme percentile values (1st and 99th) to reduce the effect of outliers.<br>
Converted numeric columns to optimal data types to save memory (e.g., float32, int8).<br>
Extracted order_date and order_month from created_at.<br>
Created derived features:<br>
AOV (Average Order Value) = grand_total / qty_ordered<br>
has_commission (flag column) for commission availability

# 2. Feature Engineering: 
Encoded categorical variables using LabelEncoder.<br>
Scaled numerical columns (price, grand_total) using StandardScaler.<br>
Aggregated customer-level data:<br>
last_order (most recent order date)<br>
orders (number of unique orders)<br>
total_spend (total amount spent)<br>
avg_order_value (average order size)<br>
recency_days (days since last purchase)

# 3. Visualization:
Monthly sales trends were plotted to observe revenue fluctuations over time.<br>
Y-axis represented total monthly sales (in scientific format like 1e8 = 100,000,000).

# 4. Modeling
Model Used: Random Forest Regressor<br>
Target Variable: grand_total<br>
Features Used<br>
price<br>
qty_ordered<br>
discount_amount<br>
Data Split: 80% training and 20% testing<br>

# 5. Model Evaluation
Metric	Score<br>
**R² Score:**	0.9726
**MAE (Mean Absolute Error):**	2186.90

✅ Interpretation:<br>
The model explains about 97.26% of the variance in total sales (grand_total), with an average prediction error of around Rs. 2186, which indicates strong model accuracy and reliable predictions.

# 6. Files Saved:
ecom_cleaned.parquet – Full cleaned dataset<br>
ecom_sample.parquet – 100K row sample for quick testing

⚙️ Technologies Used:<br>
Python, 
Pandas, 
NumPy, 
Matplotlib, 
Scikit-learn

📁 Project Structure:<br>
📦 Ecom-Sales-Analysis<br>
 ┣ 📜 ecom_cleaned.parquet<br>
 ┣ 📜 ecom_sample.parquet<br>
 ┣ 📜 README.md<br>
 ┣ 📜 ecom_analysis.ipynb<br>
 ┗ 📊 graphs/<br>

💡 Key Insights<br>

Seasonal spikes in monthly revenue were observed around late 2017.<br>
Outlier handling significantly improved model accuracy.<br>
Strong correlation between price and total order value.
