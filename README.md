<h1 align="center">🚚 Delivery Time Estimation using Linear Regression</h1>
<h3 align="center"><i>Predicting food delivery duration using operational order data</i></h3>
<h2>📝 Project Overview</h2>

This project builds a machine learning model to predict delivery time (minutes) using real delivery operational features such as:

Delivery distance

Subtotal value of order

Outstanding orders load

Order hour

Market location

Objective: Accurate ETA prediction → improved fleet planning & customer experience


LR_Delivery_Time_Estimation_Rep…

<h2>📂 Dataset Summary</h2>
Attribute	Value
File Name	porter_data_1.csv
Rows	175,777
Columns	14
Target	delivery_time (minutes)

The dataset contains timestamps, pricing details, operational load metrics & distance info.


LR_Delivery_Time_Estimation_Rep…

<h2>🔁 Workflow Pipeline</h2>
1. Load & Clean Data
2. Feature Engineering
3. Outlier Capping & Encoding
4. EDA + Visualization
5. Multicollinearity (VIF) Removal
6. Model Building – OLS Regression
7. Evaluation & Interpretation

<h2>🔨 Feature Engineering</h2>

Time-based features → order_hour, day_of_week, isWeekend

Operational load → total_outstanding_orders, busy/onshift_dashers

Pricing → subtotal, max_item_price, num_items

Geography → distance

One-hot encoding for market_id, order_protocol, order_day_of_week


LR_Delivery_Time_Estimation_Rep…

<h2>📊 Model Performance</h2>
Model	Description	Train R²	Test R²
Model 1	All features, high VIF	0.88	—
Model 2	Reduced inputs	0.75	—
Model 3 (Final)	VIF-refined regression	0.60	0.59

Final predictors retained:

distance, subtotal, outstanding_orders, order_hour,
market_id_2, market_id_3, market_id_4, market_id_5


All significant (p < 0.001).


LR_Delivery_Time_Estimation_Rep…

<h2>⭐ Key Insights</h2>
Driver	Impact
🚴 Distance ↑	Strongest driver of delay
📦 Subtotal ↑	Larger orders take longer
🔥 Outstanding Orders ↑	Queue slows delivery
🌙 Order Hour ↑	Late orders deliver faster
🏙 Markets 2–5	Faster than baseline
<h2>💡 Business Takeaways</h2>

Assign couriers with minimal distance to reduce delivery time

Queue load thresholding improves ETA consistency

Replicate strategies from fast-performing markets

Late-hour windows allow tighter ETA estimation


LR_Delivery_Time_Estimation_Rep…

<h2>📁 Repository Files</h2>
File	Description
notebook.ipynb	Model & EDA code
report.pdf	Full analysis + insights
README.md	Documentation
<h2>🚀 Future Enhancements</h2>

Random Forest / XGBoost for non-linear learning

Add weather, traffic, prep time signals

Log-transform target for tail stability

Build ETA prediction dashboard (Streamlit/API)


LR_Delivery_Time_Estimation_Rep…
